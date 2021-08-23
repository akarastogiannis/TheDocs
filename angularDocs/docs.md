# Documentation for Angular

## How to install Angular on a Machine

1. Type `npm i -g @angular/cli` in terminal.
2. Done!

## How to set up a Starter Project

1. Cd to directory.
2. Type `ng new <project-name>` in terminal.
3. Decide Yes or No for Angular Routing.
4. Decide your CSS Language of Choice.
5. Done.

## How to Start Dev Server

1. Cd to directory.
2. Type `ng serve` in terminal.
3. Open `http://localhost:4200/` on your browser.
4. Done.

## String Interpolation (Pass variable to html)

1. In export class <component-name> place the variable and type you want to add.

```
export class AppComponent {
  title: string = 'task-tracker';
}
```

2. In <component-name> html place the variable in double curly braces {{}} with variable name to display.

```
<p>{{ title }}</p>
```

## Computation in html component

```
<p> {{2+2}} </p>
```

## Javascript method in html Component

```
<p>{{ title.toUpperCase() }}</p>
```

## Ternary in html Component

```
<p>{{ 2>1? 'Hello': 'Hi' }}</p>
```

## Side Notes

* The App component is embeded in the root Html.
* Every other component we make gets embeded into the app.component.html.
* Use Typescript.s
* The Stye.css is for global style.
* 
