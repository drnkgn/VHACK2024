# Quickstart

## Cloning

Clone this repository to get started:

```bash
git clone https://github.com/drnkgn/VHACK2024
```

## Committing changes

Before committing your changes, review them with:

```bash
git status
```

Once you are satisfied with your changes, **stage**, **commit** and **push**
your changes:

```bash
# staging changes
git add <FILES TO STAGE>

# committing changes
git commit -m "YOUR COMMIT MESSAGE HERE"

# pushing changes
git push origin master
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or
`pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```
