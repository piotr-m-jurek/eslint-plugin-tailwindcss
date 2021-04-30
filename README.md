# eslint-plugin-tailwindcss

![npm (scoped)](https://img.shields.io/npm/v/eslint-plugin-tailwindcss?style=for-the-badge) ![npm bundle size (scoped)](https://img.shields.io/npm/l/eslint-plugin-tailwindcss?style=for-the-badge)

![eslint-plugin-tailwindcss logo](https://user-images.githubusercontent.com/704026/116742948-7a134980-a9f8-11eb-9953-4eb5d0c93cc1.png)

Rules enforcing best practices and consistency using [Tailwind CSS](https://tailwindcss.com/) v2.1.0

**The plugin will parse the `tailwind.config.js` file and use the correct values based on your own settings. 👍**

## Installation

You'll first need to install [ESLint](http://eslint.org):

```
$ npm i eslint --save-dev
```

Next, install `eslint-plugin-tailwindcss`:

```
$ npm i eslint-plugin-tailwindcss --save-dev
```

[eslint-plugin-tailwindcss on npm](https://www.npmjs.com/package/eslint-plugin-tailwindcss)

## Usage

Add `tailwindcss` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

```json
{
  "plugins": ["tailwindcss"]
}
```

Configure the rules you want to use under the rules section.

```json
{
  "rules": {
    "tailwindcss/classnames-order": 2,
    "tailwindcss/no-custom-classname": 2,
    "tailwindcss/no-contradicting-classname": 2
  }
}
```

Learn more about [Configuring Rules](https://eslint.org/docs/user-guide/configuring/rules).

## Supported Rules

- [`classnames-order`](docs/rules/classnames-order.md): order classnames by target properties then by variants (`[size:][theme:][state:]`)
- [`no-custom-classname`](docs/rules/no-custom-classname.md): only allow classnames from Tailwind CSS
- [`no-contradicting-classname`](docs/rules/no-contradicting-classname.md): e.g. avoid `p-2 p-3`, different Tailwind CSS classnames (`pt-2` & `pt-3`) but targeting the same property several times for the same variant.

## Upcoming Rules

- `no-redundant-variant`: e.g. avoid `mx-5 sm:mx-5`, no need to redefine `mx` in `sm:` variant as it uses the same value (`5`)

## Alternatives

I wrote this plugin after searching for existing tools which perform the same task but didn't satisfied my needs:

- [eslint-plugin-tailwind](https://www.npmjs.com/package/eslint-plugin-tailwind), not bad but no support (yet) for variants sorting
- [Headwind](https://marketplace.visualstudio.com/items?itemName=heybourn.headwind), only works within Visual Studio Code

## Contributing

You are welcome to contribute to this project by reporting issues, feature requests or even opening Pull Requests.

Learn more about [contributing to ESLint-plugin-TailwindCSS](CONTRIBUTING.md).
