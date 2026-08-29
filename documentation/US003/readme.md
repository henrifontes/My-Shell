# (My Shell) US003 – Use Case Diagram

---

## 1. Introduction

To create a general overview of the application and the roles of each actor, a **Use Case Diagram** is provided.

---

## 2. Requirements

- A **Use Case Diagram** (**UCD**) must be provided to show the main interactions between the actors and the shell system.

### 2.1 Acceptance Criteria

1. The main interactions between the actors and the system components must be provided in a **concise**, **clear**, and **understandable** manner.

### 2.2 Dependencies/References

The use cases shown in the **UCD** are based on the user stories listed in the [`user-stories.md`](../global/user-stories.md) file.

---

## 3. Relevant Information/Considerations

Some of the system components are represented as actors (`Kernel`, `File System`, and `External Programs`). It's important to state that those system components then are called _secondary actors_ in the system modeling, since they are not responsible for starting use cases. The only actor with this role is the `System User`, being so the _primary actor_ of the system. The secondary actors help the primary actor to conclude the use cases and finish its goals.
The component `File System` is a passive data store, which means it doesn't have any active role. However, it's modeled as an actor because it is an external entity to the system boundary.

Since the designing of the UCD is being made before the actual implementation of the system, the diagram might eventually have to be updated in the future.
