# link


# Summary 

**Off-Policy** refers to learning methods where the **agent learns about an optimal policy (the "target" policy) by observing data generated from a _different_ policy (the "behavior" policy).**
- **Learning Policy is not Behavior Policy:** The policy being learned or improved is separate from the policy actually used to gather experience in the environment.
- **Decoupled Learning:** This allows the agent to explore widely (using a more exploratory behavior policy) while still learning about a potentially more optimal, greedy policy (the target policy).

---

# Related Concepts

*  [[temporal difference]]
