# Projet Folder and Files Structure

```sh
src
├── assets
├── modules
|   ├── common
|   |   ├── index.ts
|   |   ├── CommonComponentFolder
|   |   |   ├── OtherCommonComponent.tsx
|   |   |   ├── OtherCommonComponent.module.css
|   ├── home
|   |   ├── components
|   |   ├── Home.tsx
|   |   ├── Home.module.css
|   |   ├── index.ts
├── hooks
├── lib
├── routes
├── store
|   ├── index.ts
|   ├── home
|   |   ├── index.ts
|   |   ├── atom.ts
|   |   ├── selectors.ts
├── services
├── test
├── types
├── utils
```

## assets

Static assets that can be versioned, otherwise the asset should be located in the `public` folder, sibling of the src.

## modules

Subfolders grouped by domain/route.

- #### common

For components that see use in multiples domains. If the component is used multiple times but in the same domain, it should be in the `components` folder of the domain instead.

- #### domain subfolder

Root of the folder should have the index, its main component (named after the folder) and a `components` folder that would have its submodules. If needed those submodules could have its own set of components etc.

### hooks

Place for the custom hooks

### lib (optional)

Can be used if we intend to import libraries so that we can handle the import in our own way afterwards. Eg : https://alexkondov.com/tao-of-react/#wrap-external-components

### routes

Routes configuration

### store

Recoil folder. Need to check if atoms/selectors can be split by domains or not.

### services

Files and methods handling API calls or Storage.

### test (optional)

Folder containing test files (unit + integration). Either have all test files in this folder or have test files moved to the same folder as the one containing the logic tested.

### types

type definitions that are used in multiple files. Component props interfaces stay in the same file as the component for simplicity.

### utils

Constants and utility functions. Need to determine if every constant/function outside of components need to be here or only the ones that are used at different places
