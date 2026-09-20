# (My Shell) US001 - Sequence Diagram

---

## 1. Introduction

In the context of the project, it's of massive importance the creation of a **_sequence diagram_** that will explain the interaction flow between the system user and the shell system. The _**sequence diagram**_ must be designed to show this interaction in an explanatory and clear way. This will be useful for anyone who wants to understand the program flow quickly and deeply.

---

## 2. Requirements

- It must be developed a _**sequence diagram**_ to demonstrate the interaction between the _**system user**_ and the _**shell system**_.

### 2.2 Acceptance Criteria

1. The **_shell system_** is a combination of **_Shell_** (interpreter) and **_Kernel_** (operating system). The SD must show the interaction between the system user and this system described.

### 2.3 Dependencies/References

No dependencies.

---

## 3. Relevant Information/Considerations

It's important to clarify what's really going on in the system illustrated in the SD designed. To do this, there are a few arrows that need to be explained more deeply:

- **3.** The raw input typed by the user and sent to the shell must be **tokenized**: the shell's lexer will be responsible for breaking down the input into single tokens.
- **4.** In between the lexical analysis and the parsing, the shell will do the expansion of some tokens, such as the expansion of environment variables (`$VAR / ${VAR}`), the expansion of the tilde (~) character, and the substitution of commands (`$(command)`).
- **5.** Word splitting is a process that splits the resultant string from an expansion into a list of words based on defined separators, defined in the `IFS` variable.
- **6.** Pathname expansion (globbing) is a process that expands wildcard characters in file names, such as `*`, `?`, and `[...]`, to match files in the filesystem.
- **7.** The `$PATH` lookup is the name resolution step for file system paths. It takes the abstract name of a command typed by the user (e.g., `cat`) and maps it to its actual physical executable on disk (e.g., `/bin/cat`), marking the final boundary before handing control over to the kernel via the execution system call.
- **12.** The `execve` system call is used with the parameters obtained from the **Tokenization and Expansion Phase**. The image of the process created via `fork()` will be fully replaced by the new program image, and the Kernel will fowardly start executing the new program in the context of the child process.
- **13.** This stage serves as the operating system's security and validation filter: it involves the kernel querying the file's metadata (inode) via the VFS layer to ensure that the file exists, is a valid program or script, and that the current user has execution permissions to run it.
- **14.** The Kernel will perform a reading to the first bytes of the file to check if it's a valid ELF binary, for what architecture it was compiled for, the entry point of the program and the program header table.
- **15.** After understanding the file's structure, the Kernel will now set up the new program's virtual addressing space by mapping the file's segments into the corresponding RAM segments in the child process address space.
- **17.** After the execution of the new program, it creates an output that will be printed to the user's terminal via fd 1, file descriptor inherited from the parent process (shell process).
