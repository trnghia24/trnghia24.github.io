# Penguin Analysis Computational Posts

This repository contains the Python and R computational posts for DSCI 521. Both posts use the Palmer Penguins dataset to investigate differences in penguin body mass and flipper length across species and the relationship between flipper length and body mass.

## Requirements

The following software was used to build the posts:

* **Quarto:** `1.10.18`
* **uv:** `0.12.7`
* **R:** `4.6.1`
* **Python:** `>=3.14`
* **renv:** bootstrapped automatically by the R project

You can check your installed versions in your **terminal**:

```bash
quarto --version
uv --version
R --version
```

## Getting started

### 1. Clone the repository

Run this in your **terminal**:

```bash
git clone https://github.com/trnghia24/trnghia24.github.io.git
cd trnghia24.github.io
```

### 2. Set up the Python environment

The Python post uses `uv` to manage its Python environment and dependencies.

Run the following commands in your **terminal**, at the repo root:

```bash
uv sync
```

This creates or updates the project's virtual environment using the dependencies recorded in `pyproject.toml` and `uv.lock`.

### 3. Set up the R environment

Open the project in **RStudio/Positron** and start an **R Console**.

Run the following in the **R Console**, at the repo root:

```r
renv::restore()
```

`renv::restore()` installs the R packages recorded in `renv.lock`. The `renv` project environment is activated automatically when the project is opened.

### 4. Build the computational posts
Run the following command in a terminal from the repository root:

```bash
uv run quarto render
```

This renders the entire Quarto project, including both the Python and R computational posts. The Python post is executed using the project's uv environment, while the R post uses the project's active renv environment.

To preview the complete site locally:

```bash
quarto preview
```

#### Viewing the built site

The rendered HTML files are created in the `docs/` directory.

After rendering, the main site can be opened locally by running this command in the **terminal** on macOS.:

```bash
open docs/index.html
```

Alternatively, open the generated `.html` files inside `docs/` directly in a web browser.

For interactive development, you can preview the site by running this in the **terminal** from the repository root:

```bash
quarto preview
```

Quarto will build the documents and open a local preview in your browser. The preview updates as the source files are changed.

### 5.Data

Both computational posts use the **Palmer Penguins** dataset.

The dataset comes from the Palmer Penguins project:

https://allisonhorst.github.io/palmerpenguins/

The Palmer Penguins data are available under the **CC0 1.0 Universal** license.

#### Network requirements

The build does **not** require an internet connection to download the dataset each time the site is rendered. The Python post loads the dataset through the installed `palmerpenguins` package, while the R post uses the dataset provided by the installed `palmerpenguins` R package.

However, an internet connection may be required during initial environment setup if the required Python or R packages are not already available locally:

```bash
uv sync
```

and, in the **R Console**:

```r
renv::restore()
```

Once the environments and dependencies have been installed, the Quarto build itself can be run locally without fetching the dataset from the web.
