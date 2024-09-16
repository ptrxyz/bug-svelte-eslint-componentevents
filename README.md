# Repo to show a possible bug with eslint-parser-svelte

Relevant files: 
- src/routes/+page.svelte
- src/routes/component.svelte

Run `npm run bug` to run eslint on the relevant file.

Problem:
As you can see in `component.svelte`, the event `foo` is typed as an object and the VSCode extension correctly detects the type of `X` upon hover.

![image](https://github.com/user-attachments/assets/3dc53b4f-3af2-4600-a3d6-e8a6301ddf9d)

However -- when running eslint on `+page.svelte`, there is a linter error indicating that `X` is typed as `any` for the eslint:
`'any' overrides all other types in this union type  @typescript-eslint/no-redundant-type-constituents`

![image](https://github.com/user-attachments/assets/a34f6f45-88c6-4835-81a5-b55c2045e096)


Further testing with other type-checked rules (i.e. `@typescript-eslint/no-unsafe-assignment` and `@typescript-eslint/no-unsafe-member-access`) also show that `X` is simply `any` for eslint.

This is a problem since my CI can't catch a lot of errors then and type-safety goes down the drain. 
