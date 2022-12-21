# This is a documentation that guides developers to develop the platform

## Project structure

The project is structures into modules which can be found in the src/modules directory.

Current directories are:

- [components](src/modules/components/index.ts)
- [hooks](src/modules/hooks/index.ts)
- [models](src/modules/models/index.ts)
- [pages](src/modules/pages/index.ts)
- [services](src/modules/services/index.ts)
- [states](src/modules/states/index.ts)
- [utils](src/modules/utils/index.ts)

Each module will have an index.ts file which exports the classes or the functions of the module globally.

Every sub-module in the project shall have an index.ts file to export the classes or the functions to the parent module.

**! Avoid importing the functions from a sub-module into the working directory, directly. Use the parent module's _index.ts_ file to import.**

For every new module:

- Create it under the modules directory in src/modules.
- Create an index.ts file.
- Include the path of the newly created module into the alias object in vite.config.ts.
- In the vite.config.ts, all alises should be prefixed with an @.

## Component development

Every reusable element in the application will be build into a generic component.

Each and every component lies under the [components module](src/modules/components).

Naming convention:

- All component filenames are named using lowercase characters with underscores ( \_ ) for space.
- Components are structured into their own directories
  - Naming convention for the directory name remains same as that of the component file.
  - Every component consists 3 files:
    - component_name.component.tsx - Consists of all the code and implementation related to the component. .component.tsx is used to distinguish between a component file and other f
    - styles.module.scss or styles.scss - Contains all the styles related to the component. .module.scss is used to restrict the scope of the styles to the component.
    - component_name.test.ts - Contains all of the tests related to the component.
- It is adviced to write test cases for all the components to avoid unintended failures during production builds.
