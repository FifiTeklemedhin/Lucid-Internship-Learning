# What I learned from my second commit!

* if you cannot see your replacement component despite copying all other required properties of the old component, then make sure that you have **imported* the `module` in the `.module.ts` file
    * an example here (*note that the component name is in `upper camelcase` with `"Module"` at the end):
        * at the top: `import {LucidButtonModule} from '@lucid/angular/coreux/button/button.module';` 
        * in the `imports[]` list: LucidButtonModule
* when replacing a `lucid-icon` component with a `lucid-button`, make sure to **delete** any `class` attributes starting with `lucid-icon` as they won't be relevant to a button.