# {{cookiecutter.project_name}}
This project contains three folders:
```
.
├── docs
├── pyproject.toml # project configuration file with `uv` dependencies
├── _quarto.yml # a quarto and quartodoc configuration file
├── README.md # this README
├── scripts # uv scripts with self-contained dependencies which use typer
├── src
├── tests
└── uv.lock # uv lock file
```

## `docs`
For documentation:
```
quarto create
```
was used to configure the project as a quarto project, allowing both research and code documentation to be rendered using `uv run quartodoc build` and `quarto preview`. The `docs` folder contains:  
```
docs
├── notebooks # used for exploratory and interactive data analysis using `Marimo`
│   └── index.qmd
├── reference # `quartodoc` reference documentation of `src`
│   └── index.qmd
└── research # `quarto` literature reviews, system specifications or presentations
    └── index.qmd
```
These documents serve as a comprehensive resource for understanding the project, its structure, and its implementation details. They are intended for both internal use, providing valuable insights into the project's objectives and methodologies.  Additionally, they can be useful for onboarding new team members or for stakeholders who need to familiarize themselves with the project. By maintaining clear and organized documentation, we can ensure that knowledge is preserved and easily accessible throughout the project's lifecycle.

## `scripts`
`uv` defines a way to specify [scripts and their dependencies in a project](https://docs.astral.sh/uv/guides/scripts/#declaring-script-dependencies). In this folder, we use [`typer`](https://typer.tiangolo.com/) to create command-line interfaces for our scripts.

## `src`
This project was created by running:
```
uv init --package
```
this created our python `src` directory, as well as `pyproject.toml`.

## `tests`
This project uses `pytest` for testing. The tests are located in the `tests` directory and can be run with:
```
pytest
```
