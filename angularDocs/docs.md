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

1. In export class **component-name** place the variable and type you want to add.

```
export class AppComponent {
  title: string = 'task-tracker';
}
```

2. In **component-name** html place the variable in double curly braces {{}} with variable name to display.

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

## @Input, Sending data to a child Component from Parent

1. Add Component specific properties in the child component tag in the Parent. Notice the color and text attributes.

```
<app-button color="green" text="Add"></app-button>
```

2. In the child component.ts file add the Import `Input` from angular/core.

```
import { Component, OnInit, Input } from '@angular/core';
```

3. Also when exporting the child class component in the child component.ts file, add their input calls. Notice how you must add a starting values for the attributes just in case you do not provide specific values for the attributes in the parent component.

```
export class ButtonComponent implements OnInit {
  @Input() text: string = 'Click';
  @Input() color: string = 'blue';

  constructor() { }

  ngOnInit(): void {
  }
```

4. Then in the child component.html add the text attribute with double curly brackets.

```
<button class="btn">{{ text }}</button>
```

5. Now for the specific color attribute, you must use `ngStyle` directive in brackets and curly bracktes and qutation marks.

```
<button  [ngStyle]="{'background-color': color}" class="btn">{{ text }}</button>
```

6. Done.

## onClick handler for button in Component <Part 1>

1. In **< component-name >.component.html** in the button tag add an click method to method name. Notice the `(click)="onClick()"` this means you want to make clickable and connected to a method named 'onClick'.

```
<button  
    [ngStyle]="{'background-color': color}" 
    class="btn"
    (click)="onClick()"
>
    {{ text }}
</button>
```

2. Then in **< component-name >.components.ts** file when you are exporting the button add the method we named 'onClick()'. Notice the `onClick()` method we added and for the example we have the button log a 'Add Clicked' message when clicked.

```
export class ButtonComponent implements OnInit {
  @Input() text: string = 'Click';
  @Input() color: string = 'blue';

  constructor() { }

  ngOnInit(): void {
  }

  onClick() {
    console.log("Add Clicked");
  }

}
```

3. Done.

## Output for onClick handler EventEmitter (To make the button function more re-usable) <Part 2>

1. Import `Output` and `EventEmitter` from angular/core.

```
import { Component, OnInit, Input, Output, EventEmitter } from '@angular/core';
```

2. In export class of the component create an Output EventEmitter function. And reference it in the onClick function.

`  @Output() btnClick = new EventEmitter();`

```
 /* Handle the button click */
  onClick() {
    this.btnClick.emit();
  }
```

```
export class ButtonComponent implements OnInit {
  @Input() text: string = 'Click';
  @Input() color: string = 'blue';
  @Output() btnClick = new EventEmitter();

  constructor() { }

  ngOnInit(): void {
  }

  /* Handle the button click */
  onClick() {
    this.btnClick.emit();
  }

}
```

3. Then in the **< parent-name >.component.html** that houses an instance of that child component you can then refrence that function name to push it to do your own function in the **< parent-name >.component.ts** file.

`<app-button color="green" text="Add" (btnClick)="toggleAddTask()"></app-button>`

4. And then in **< parent-name >.component.ts** you can add the function you want it to do, in export class.

```
toggleAddTask() {
    console.log("Add Clicked");
  }
```

```
export class HeaderComponent implements OnInit {
  title: string = 'task-tracker';

  constructor() { }

  ngOnInit(): void {
  }

  toggleAddTask() {
    console.log("Add Clicked");
  }

}
```

5. Done

## Create an Interface (Schema/Rules) for a Data Structure <Part 1>

1. Add in the app folder the name of the Interface (Preferably starting with a capital letter).

`Task.ts`

2. Then in `Task.ts` you want to make the interface exportable so you declare it like this.

```
export interface Task {
    /* id has question mark b/c its not needed when creating a new task */
    id?: number;
    text: string;
    day: string;
    reminder: boolean;
}
```

3. Then in your Data Structure (Ex. Json File) you need to import it and set its type to the interface you created.

`import { Task } from './Task';`

`export const TASKS: Task[] = [`

```
/* We also have to import Task here */
import { Task } from './Task';

/* We add the type, which is Task, and it is an array Task[] */
export const TASKS: Task[] = [
  {
    id: 1,
    text: 'Doctors Appointment',
    day: 'May 5th at 2:30pm',
    reminder: true,
  },
  {
    id: 2,
    text: 'Meeting at School',
    day: 'May 6th at 1:30pm',
    reminder: true,
  },
  {
    id: 3,
    text: 'Food Shopping',
    day: 'May 7th at 12:30pm',
    reminder: false,
  },
];
```
4. Angular might import it and set its type automatically.

5. Done.

## How to use interface in a Component <Part 2>

1. First create a new component in the components folder using ng generate.

`ng generate component components/tasks`

2. In the **< component-name >.component.ts** file you want to import the json data and the interface.

`import {TASKS} from '../../mock-task';`

`import {Task} from '../../Task';`

3. Then you want to make it usuable in that component by adding it into the export class of that component.

`tasks: Task[] = TASKS;`

4. Overall it should look like this.

```
import { Component, OnInit } from '@angular/core';
import {Task} from '../../Task';
import {TASKS} from '../../mock-task';

@Component({
  selector: 'app-tasks',
  templateUrl: './tasks.component.html',
  styleUrls: ['./tasks.component.css']
})
export class TasksComponent implements OnInit {
  tasks: Task[] = TASKS;

  constructor() { }

  ngOnInit(): void {
  }

}
```

5. Done.

## Side Notes

* The App component is embeded in the root Html.
* Every other component we make gets embeded into the app.component.html.
* Use Typescript.s
* The Stye.css is for global style.
* Use `ngOnInit()` in component.ts file in component folder most of the times when you initalize some code
