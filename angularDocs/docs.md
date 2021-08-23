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

## How to create a new Component

1. Cd into dir.
2. Type: `ng generate component <component-name>`.
3. Done.

## How to create a new Component in a folder

1. Cd into dir.
2. Type: `ng generate component <folder-name>/<component-name>`.
3. Ex: `ng generate component component/footer`.
4. Done.

## Add custom component to App Component

1. Add selector in custom component (should be auto generated).

```
@Component({
  selector: 'app-header',
  templateUrl: './header.component.html',
  styleUrls: ['./header.component.css']
})
```

2. Take the selector `app-header` and place in App component html as a tag.

```
<app-header></app-header>
```

3. Now whatever is in header.component.html is now also in app.component.html at that exact location.

```
Output:<br>
header works!
```

4. Done.

## Side Notes

* The App component is embeded in the root Html.
* Every other component we make gets embeded into the app.component.html.
* Use Typescript.s
* The Stye.css is for global style.
* Use `ngOnInit()` in component.ts file in component folder most of the times when you initalize some code
