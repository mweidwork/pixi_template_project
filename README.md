# 🧩 Pixi Template Project

A [Copier](https://copier.readthedocs.io/en/stable/) template for creating Python projects with [Pixi](https://github.com/prefix-dev/pixi) as the environment and dependency manager.

For full documentation, see the [official Pixi docs](https://pixi.sh).

## Usage

### 1. Install copier

```bash
pip install copier
```

### 2. Create a new project from this template

```bash
copier copy --trust https://github.com/mweidwork/pixi_template_project <destination-path>
```

Follow the interactive prompts to configure the new project.

---

<details>
<summary>🧰 Using Pixi</summary>

After generating the project:

```bash
cd <destination-path>
```

Initialize and activate the Pixi environment:

```bash
pixi install      # Installs dependencies for all defined environments
pixi shell        # Opens the managed shell
```

Run common tasks:
```bash
pixi run postinstall     # Installs the package in editable mode
pixi run test            # Runs tests with pytest
pixi run lint            # Runs linting and formatting checks
pixi run pre-commit-all  # Runs all pre-commit hooks
```

When multiple environments are defined:
```bash
pixi run -e dev <task>   # Runs a task inside the dev environment
pixi run -e lint ruff check .
```
</details>

---

<details>
<summary>🔧 Managing Dependencies with Pixi</summary>

Pixi provides commands to **add**, **update**, and **remove** dependencies for specific environments or features.

---

<details>
<summary>➕ Add a Package</summary>

Add a new dependency to the **default environment**:

```bash
pixi add requests
```

Add a dependency to a **specific feature or environment** (for example, `test` or `lint`):

```bash
pixi add pytest -e test
pixi add ruff -e lint
```

Add a package with version constraints:

```bash
pixi add "pandas>=2.0"
```
</details>

---

<details>
<summary>🔄 Update Dependencies</summary>

Update all dependencies to the latest compatible versions:

```bash
pixi update
```

Update a specific package:

```bash
pixi update requests
```

Pixi automatically updates the lockfile to ensure deterministic builds.
</details>

---

<details>
<summary>➖ Remove a Package</summary>

Remove a package from the **default environment**:

```bash
pixi remove requests
```

Remove from a specific environment:

```bash
pixi remove pytest -e test
```
</details>

</details>
