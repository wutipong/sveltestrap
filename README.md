![Unit Tests](https://github.com/Sveltestrap/sveltestrap/actions/workflows/unit.yml/badge.svg)

![sveltestrap](https://github.com/sveltestrap/sveltestrap/assets/1918732/9e00bb52-01ac-44ba-a79e-46922fcdfea6)
## Bootstrap 5 Components for Svelte 4+

Sveltestrap is a library designed to simplify the integration of [Bootstrap 5](https://getbootstrap.com) components into your [Svelte](https://svelte.dev) applications. It eliminates the need for Bootstrap component classes, the inclusion of Bootstrap's JavaScript, and reliance on jQuery.

This open-source software is freely available under the permissive MIT license. It draws inspiration from the [reactstrap](https://reactstrap.github.io/?path=/story/home-installation--page) library for [React](https://react.dev/).

Please note that Sveltestrap <u>**does not directly embed Bootstrap style**</u>. To use Bootstrap themes effectively, you must include Bootstrap 5 CSS using one of the methods outlined below.

**Note**
If you looking for Svelte 3.x support, you can use the original [sveltestrap](https://github.com/bestguy/sveltestrap) package.

[![slack](https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white)](https://join.slack.com/t/sveltestrap/shared_invite/zt-28y9c8a8k-6~9UI~26Cx7pF1JKeQZPyA)

---

## Install

```bash
# npm
> npm install svelte @sveltestrap/sveltestrap

# pnpm
> pnpm install svelte @sveltestrap/sveltestrap

# yarn
> yarn add svelte @sveltestrap/sveltestrap
```

## Bootstrap CSS

It's essential to note that Bootstrap 5 components do not come with Bootstrap styles preloaded, so you'll need to add the stylesheet manually. Here's how you can add them:

1. Add to your apps static `index.html` file
```html
<head>
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
  />
</head>
```

2. Add to your main `App.svelte` file
```html
<svelte:head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
</svelte:head>
```

3. Import the styles directly in your CSS bundle

```html
<style>
  @import 'https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css';
</style>
```

4. Use the provided [Styles](/?path=/docs/components-styles--docs) component

```html
<script>
  import { Styles } from '@sveltestrap/sveltestrap';
</script>

<Styles />
```

Then use Sveltestrap components in your svelte component:

```html
<script>
  import { Button, Col, Row } from '@sveltestrap/sveltestrap';
</script>

<Row>
  <Col>
    <Button color="primary" outline>Hello World!</Button>
  </Col>
</Row>
```

## Bootstrap Icons

If you want to use the [Icon component](https://sveltestrap.js.org/?path=/story/components--icon),
you also must include a link to Bootstrap Icon CSS, for example:

Include it in your app's `App.svelte`:

```html
<svelte:head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.5/font/bootstrap-icons.css">
</svelte:head>
```

or you can include it in your app's `index.html`:

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.5/font/bootstrap-icons.css"
/>
```

or the [Styles](https://sveltestrap.js.org/?path=/story/components--styles) component includes the Bootstrap Icon CSS by default:

```html
<script>
  import { Styles } from '@sveltestrap/sveltestrap';
</script>

<Styles />
```

## Using Sapper

If you are using Sveltestrap with Sapper, it's recommended you import the component source directly.
Note that this issue does not affect SvelteKit.

```html
<script>
  import { Button, Col, Row } from '@sveltestrap/sveltestrap/src';
</script>

<Row>
  <Col>
    <Button color="primary" outline>Hello World!</Button>
  </Col>
</Row>
```

If you prefer the '@sveltestrap/sveltestrap' import, you can move the package to `devDependencies` block in your `package.json` so that sapper will parse the es bundle

```json
"devDependencies": {
    "@sveltestrap/sveltestrap": "*.*.*",
    ...
  },
```
