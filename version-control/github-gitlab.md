# Github / Gitlab

The **best format for GitHub commit naming convention**—followed by many experienced developers and major projects—adheres to a combination of _clarity, consistency, and structure_ rooted in industry best practices and the "Conventional Commits" standard.

**Recommended Commit Message Format:**

```
text<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

**Guidelines & Conventions:**

* **Type:** Indicates the nature of the change (e.g. `feat`, `fix`, `chore`, `refactor`, `docs`).
* **Scope (optional):** Modular area or feature affected (e.g. `auth`, `UI`).
* **Subject:** Brief, imperative description of the change (max \~50 characters, no period)
* **Body (optional):** More detailed motivation and context (wrap at 72 characters)
* **Footer (optional):** References to issues, breaking changes, etc.

**Examples of Good Commit Messages:**

* `feat(auth): add JWT-based authentication`
* `fix(login): resolve race condition in login flow`
* `refactor(core): split logic into separate module`
* `chore: update dependencies`
* `docs(readme): add usage instructions.`

**Other Best Practices:**

* Use the **imperative mood** in the subject (e.g. "Add…" not "Added…")
* Separate the subject from the body with a blank line.
* Keep commits **atomic**: each commit should make a single logical change.
* Be **specific and concise**; avoid vague terms.
* Reference issues in the footer (e.g., `Closes #42).`

**Summary Table: Conventional Commit Types**

| Type     | Purpose                                       | Example                                 |
| -------- | --------------------------------------------- | --------------------------------------- |
| feat     | New feature                                   | feat(api): add user search endpoint     |
| fix      | Bug fix                                       | fix(ui): correct button alignment       |
| chore    | Maintenance or build tasks                    | chore: update code formatting           |
| refactor | Code change not adding/removing functionality | refactor(auth): simplify token handling |
| docs     | Documentation changes                         | docs(readme): add setup instructions    |
