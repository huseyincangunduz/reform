# Attention: This project will not be maintained anymore and i have no relationship with that organisation. You can follow me on [Linkedin](https://www.linkedin.com/in/huseyincgunduz/), Github (huseyincangunduz) or instagram (hcangunduz.dev) for fore open source libraries and etc.

# ReformJS

![ReformJS](./assets/images/reform-logo.png)

ReformJS is a Javascript library developed for building form in detail, validating and managing easily.
All definitions, validations are made with a object. Inputs, elements are placed according to these definitions.
And all value changes are tracked by Reflectors. Values is placed by sections and made ready for use.

## Getting Started

You can install ReformJS via

`npm install @morphosium/reform`

or

`yarn add @morphosium/reform`

or

`<script src="./path-of/public/bundle/reform.js">`

Code implementation will be like this

```
/** You can consider use import or require if installed by npm / yarn
    import { Reflector, InputField, SectionField, EventObserve } from "@morphosium/reform";
 */
const { Reflector, InputField, SectionField, EventObserve } = Reform
const reflector = new Reflector(
    {
        content: [
            new InputField({
                name: "name",
                label: "Name",
            }),
            new InputField({
                name: "lastname",
                label: "Lastname",
            }),
            /* Sections is represents values group.
            At the final value: State, City and Streets values will be under "address" field */
            new SectionField({
                name: "address",
                content: [
                    new InputField({
                        name: "state",
                        label: "State",
                    }),
                    new InputField({
                        name: "city",
                        label: "City",
                    }),
                    new InputField({
                        name: "street",
                        label: "Street",
                    }),
                ]
            })
        ]
    }
);

/* Form elements will be added into div element those id "base" */
reflector.expandThere("#base");

/* Each value changes notified and new value is written into console */
reflector.onValueChange.subscribe(
    new EventObserve(
        () => {
            console.info(reflector.getValue())
        }
    )
)
```

In any browser screen, shown as like following

![reform browser screen](assets/images/browser-screen.jpg)

At the same time,at each value change of any input, new value is written in console like this

![reform console output](assets/images/console-output.png)

## Terminology

**Initial fields** represents form build instructions.

Initial fields are separated within itself as _InputField_, _ElementField_ and _SectionField_

**InputFields** are user input instructions contains _name, label, validations_ and etc.

**ElementField** represents HTMLElement, contains another InitialFields. But at the reflecting into browser, inputs will be seperated according ElementField definitions.

**SectionField** represents object at the value, contains child input and section values

**Reflector** builds form on the screen by provided instructions. At needed, values and validation issues can be fetched from reflector.

and _(In development for now)_ another reflections of initial fields can be made some changes by reaching reflector.

## Detailed info

You can get documentation on [https://morphosium.com/projects/reform/documentations/1.1.0/]

## Roadmap

We are planning develop that framework for our requirements. At the future, We decided to add following features

- "Select" input with options

- Initial field definition as HTML-Similar format

- Translation of validation messages (Firstly Turkish)

- Instantly changes of Reflections state

At the same time. New features planned are going to be in "projects" page of github page

In this development progress, your feedbacks, improvements, (and if you wish, contribution) will be welcomed

## Contact

- Hüseyin Can Gündüz

  - github: @huseyincangunduz

  - instagram: @hussainlobo

  - twitter: @hcangunduz

  - email: hcangunduz@gmail.com

- Repo issues tab
