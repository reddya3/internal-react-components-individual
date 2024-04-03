# Modular React Component Library for PPE

 PPE Modular React Component Library, a collection of individually packaged React components designed for reuse across various projects.

## Overview

This library is structured to support modular packaging, allowing consumers to install only the components they need, thereby optimizing their application's bundle size and improving load times. Each package is hosted on Artifactory, ensuring secure and convenient access within our organization.

The library currently includes the following packages:
- `@ppe/ppe-react-button`: A React button component styled according to Leyden design guidelines.
- `@ppe/ppe-react-styleguide`: SCSS stylesheets comprising the core styling used across PPE projects.
- `@ppe/ppe-react-table`: A set of React components for building tables, including Body, Cell, Grid, Head, Header, and more.

## Getting Started

### Authentication with Artifactory

Before installing the packages, authenticate with Artifactory to securely fetch the necessary NPM packages:

```bash
curl -u<artifactory_username>:<artifactory_password> https://rt.artifactory.tio.systems/artifactory/api/npm/npm-ppe-internal-virtual/auth/ppe >> .npmrc
```

Replace `<artifactory_username>` and `<artifactory_password>` with your actual Artifactory credentials.

### Installing Components

Install the desired components using NPM:

```bash
npm install @ppe/ppe-react-button
npm install @ppe/ppe-react-styleguide
npm install @ppe/ppe-react-table
```

## Package Specific Instructions

### @ppe/ppe-react-button

**Description**: This package provides a React button component, offering various styles as defined in the PPE Style Guide.

**Usage**:

```javascript
import { Button } from '@ppe/ppe-react-button';

<Button onClick={() => console.log('Button clicked')} type="secondary">
  Button Text
</Button>
```

**Build and Publish**:

To build and publish changes to this package:

1. Run `npm run build` to compile the package.
2. Update the version in `package.json`.
3. Run `npm publish --scope=@ppe` to publish to Artifactory.

### @ppe/ppe-react-styleguide

**Description**: Contains SCSS stylesheets that encapsulate the core styling for PPE applications.

**Usage**:

In your main SCSS file:

```scss
@use "@ppe/ppe-react-styleguide/dist/els-styleguide-core";
```

### @ppe/ppe-react-table

**Description**: A collection of React components for constructing tables, including `Body`, `Cell`, `Grid`, `Head`, `Header`, `HeaderCell`, `HeaderRow`, `Row`, `Table`, and `WrapperRow`.

**Usage**:

```javascript
import { Table, Row, Cell } from '@ppe/ppe-react-table';

<Table>
  <Row>
    <Cell>Data</Cell>
  </Row>
</Table>
```
