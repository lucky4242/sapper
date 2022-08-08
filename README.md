# sapper-template

The default template for setting up a [Sapper](https://github.com/sveltejs/sapper) project. Can use either Rollup or webpack as bundler.

## Please note

Sapper is no longer being actively developed. You may be interested in using Sapper's succesor, [SvelteKit](https://kit.svelte.dev/) for new projects.

## Getting started

### Using `degit`

To create a new Sapper project based on Rollup locally, run

```bash
npx degit "sveltejs/sapper-template#rollup" my-app
```

For a webpack-based project, instead run

```bash
npx degit "sveltejs/sapper-template#webpack" my-app
```

[`degit`](https://github.com/Rich-Harris/degit) is a scaffolding tool that lets you create a directory from a branch in a repository.

Replace `my-app` with the path where you wish to create the project.


### Using GitHub templates

Alternatively, you can create the new project as a GitHub repository using GitHub's template feature.

Go to either [sapper-template-rollup](https://github.com/sveltejs/sapper-template-rollup) or [sapper-template-webpack](https://github.com/sveltejs/sapper-template-webpack) and click on "Use this template" to create a new project repository initialized by the template.


### Running the project

Once you have created the project, install dependencies and run the project in development mode:

```bash
cd my-app
npm install # or yarn
npm run dev
```

This will start the development server on [localhost:3000](http://localhost:3000). Open it and click around.

You now have a fully functional Sapper project! To get started developing, consult [sapper.svelte.dev](https://sapper.svelte.dev).



