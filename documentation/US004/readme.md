# (My Shell) US004 – Domain Model

---

## 1. Introduction

To provide a deeper view of the system domain, that is its entities, relationships, objects, and attributes, a **Domain Model** must be created.

---

## 2. Requirements

- A **Domain Model** (**DM**) must be created to represent the system domain concepts and their relationships within the system.

### 2.1 Acceptance Criteria

1. The **Domain Model** must represent the main domain concepts of the shell (at least `Command`, `Token`, `Process`, `Job`, `Environment`, `Variable`, `Redirection`, and `Pipeline`) as entities, each with its relevant attributes, and every entity must be connected to at least one other through a labeled relationship (association, aggregation, or composition) with multiplicities defined at both ends.

### 2.2 Dependencies/References

- The relationships between the domain entities and concepts are defined based on the line of reasoning established by the user stories document [`user-stories.md`](../global/user-stories.md).
- The modeling and relationships of the system domain concepts are based on the program flow described in the [Sequence Diagram](../global/images/SD.svg).

---

## 3. Relevant Information/Considerations

### Definitions

- **Alias**: a user-defined shortcut for a command.
- **Command**: a directive given by the user to the shell to perform a specific action.
- **Environment**: the set of variables that define the context in which a process runs.
- **Input**: raw data entered into the shell (via a Shell Script file or keyboard) before being parsed.
- **Job**: an abstract unit of work used by the shell that contains a group of processes with the same *group ID* (PGID) that is submitted to the system for execution.
- **Kernel**: the core component of the operating system that manages computer resources and provides services for running programs.
- **Output**: data produced by the shell as a result of executing a command.
- **Pipeline**: a sequence of commands connected by pipes, where the output of one command is used as the input for the next command.
- **Process**: an instance of an executing program.
- **Program**: an executable file (or script) stored on disk containing instructions that can be loaded into memory and executed by the operating system.
- **Prompt**: the text displayed to the user to indicate that the shell is waiting for input.
- **Redirection**: the process of changing the standard input, output, or error streams (_stdin_, _stdout_, _stderr_) of a command to read from or write to a file or file descriptor.
- **Session**: a period of time during which a user interacts with the shell. In a broader definition, it consists of a collection of process groups in a controlling terminal.
- **Shell**: a program that receives commands from the user, processes them, asks the operating system to execute them, and then returns the output to be printed on the screen. It's the interpreter and intermediary between the user interface and the operating system.
- **Signal**: a notification sent to a process to indicate that an event has occurred.
- **Syscall**: a request made by a process to the kernel to perform a system-level operation.
- **Terminal**: the user interface that allows the user to interact with the shell. It's the program that provides the graphical interface for the user to input commands and then see the output.
- **Token**: a sequence of characters that represents a single unit of meaning in the command line.
- **Variable**: a named storage location holding a key-value pair that stores state within the shell. If exported (becoming an _environment variable_), it is placed in the _environment array_ passed to child processes upon execution.
