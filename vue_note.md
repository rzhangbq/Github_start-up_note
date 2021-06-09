# Vue Notes

## 1. Bindings

1. {{}}

	- `{{ yourName }}`
	- `{{ yourAgeIn5() }} in 5 years`
	- `{{ Math.random() }}`
2. v-html
   - `<p v-html="outputGoal()"></p>`
3. v-bind

   - **short cut: `v-bind:`->`:`**
   - `<img v-bind:src=imageLink />`
   - `<input type="text" v-bind:value="showYourGoal" />`
4. v-on *calling a function on some event*
   - **short cut: `v-on:`->`@`**
   - `<button v-on:click="addCounter(4)">Add</button>`
   - `<button v-on:click.right="reduceCounter(4)">Remove</button>`
   - `<input type="text" v-on:keyup.enter="setName($event, 'ZHANG')" />`
   - `<input type="text" v-on:input="refreshOutputWhenInput" />`
     - To get value from input: `this.upperOutput = event.target.value;`
5. v-model *double binding with a certain variable*

   - `<input type="text" v-model="lowerOutput" />`

## 2. Watch, computed and methods

```mermaid
graph
A(Methods) --> B[Execute when anything changes] --> C[For data that really needs to be re-evalued all the time] --> K["() needed after function name"]
D(Computed) --> E[Execute when any depending data changes] --> F[For data that depends on other data] --> L["() not needed after function name"]
H(Watch) --> I[Execute in reaction to some data change] --> J[For any non-data update] --> M["not for {{}}"]
```

### Javascript setTimeout

```javascript
setTimeout(function () {
  ……;
}, 1000); // ms
}
)
```

## 3. Vue-controlled style
