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

It is important to note that the `External Program` component is a _secondary actor_ in the system model, as it is not responsible for initiating use cases. The only actor initiating interactions is the `System User`, who serves as the _primary actor_. Secondary actors assist the primary actor in fulfilling use cases and achieving their goals.

Furthermore, as the Use Case Diagram (UCD) is designed prior to the actual implementation of the system, it represents an iterative artifact that may be updated as the development progresses.
