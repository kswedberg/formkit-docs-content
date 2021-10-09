# Inputs

FormKit’s inputs are similar to HTML inputs but turbocharged with much needed features like labels, help text, validation, and error messages (and much more). Similar to how HTML’s `<input>` tag uses various `type` attributes (ie `<input type="text">` vs `<input type="checkbox">`) FormKit uses the `type` prop for _all_ inputs — in fact __with FormKit there is only 1 component you have to learn__:

<code-example
  name="Text input"
  file="/_content/examples/single-component/single-component"
  langs="vue">
</code-example>

FormKit inputs are not confined to what is available in "native" HTML. [FormKit Pro](/pro) for example, uses "synthetic" input types like `autocomplete`, `taglist` and `wysiwyg`. Of course, you can write your own inputs too by creating [custom inputs](/guides/custom-input).

## Setting values
<!-- vue-specific -->
There are 4 ways to set the value of an input:

- Using the `value` prop.
- Using `v-model`.
- Using FormKit's node `input` method.
- Setting the value of a parent `FormKit` component.

### Using `value` prop

You can set the value of a single input, or a group of inputs using the `value`
prop.

<code-example
  name="Value prop"
  file="/_content/examples/value-prop/value-prop"
  langs="vue">
</code-example>

<callout type="warning">
The <code>value</code> prop should only be used for setting the <em>initial</em> value of an input. It will not react to changes after the component has been created.
</callout>

### Using `v-model`
<!-- vue-specific -->
Using `v-model` allows for two-way reactive data binding with any FormKit input.


<code-example
  name="Input v-model"
  file="/_content/examples/v-model/v-model"
  langs="vue">
</code-example>

## Setting attributes

In nearly all cases, any attributes on the `<FormKit>` component will be passed through to the actual input element at the heart of the component. For example:

<code-example
  name="Text input"
  file="/_content/examples/attributes/attributes"
  langs="vue">
</code-example>

## Universal props

FormKit inputs accept both universal props (ones that apply to all FormKit inputs), and input-specific props. The following table is a comprehensive list of props available to all FormKit inputs.

Prop       |  Default    | Description
-----------|-------------|------------------------------------------------------
delay      | `20`        | Number of milliseconds to debounce an input's value before the `commit` [hook](/essentials/hooks) is dispatched.
name       | `{type}_{n}`| The name of the input as identified in the data object. This should be unique within a group a fields.
schema     | `{}`        | An object of composition-key to schema partials, where each schema partial is applied to the respective composition-key
type       | `text`      | The type of input to render.
validation | `[]`        | A string or an array of [validation rules](/essentials/validation).