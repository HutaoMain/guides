1. how to create new angular project
   CLI: ng new [project name]

2. how to create component
   CLI: ng generate component [component name]
   CLI: ng generate component [component name] --skip-tests // to skip test files

3. how to generate interface
   CLI: ng generate interface [folder]

4. How to props from parent to child

Parent component typescript
sampleObject: Interface = {
sampleId: 999,
sampleName: "myName"
}

Parent html
<child-component [sampleObject]="sampleObject"></child-component>

child component typescript
Input() sampleObject!: Interface;
