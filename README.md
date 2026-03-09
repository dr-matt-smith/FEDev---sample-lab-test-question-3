[back to assessments](https://github.com/dr-matt-smith/FEDev---assessment-samples-and-walkthroughs?tab=readme-ov-file) <<<

[Question 1](https://github.com/dr-matt-smith/FEDev---sample-lab-test-question-1)
| [Question 2](https://github.com/dr-matt-smith/FEDev---sample-lab-test-question-2)
|
Question 3
| [Question 4](https://github.com/dr-matt-smith/FEDev---sample-lab-test-question-4)
| [Question 5](https://github.com/dr-matt-smith/FEDev---sample-lab-test-question-5)
| [Question 6](https://github.com/dr-matt-smith/FEDev---sample-lab-test-question-6)


# FEDEv - SAMPLE lab test question 3

The "brief" for the test is a PDF file in directory "brief"

NOTE:
**no use of AI is permitted in the lab test**

There are videos for each of the 6 questions:


The files in this repo are the solution I created to this sample test
- you may use any editor available on the university PCs
  - I used Celbridge, which you may install on the lab PCs if you wish

## Question 3 - video

- question 3
  - https://go.screenpal.com/watch/cOehrenZFbD
  - 7mins 57secs


## Question 3a - Route with data `/oddeven/<n>`

We need to create a directory `/routes/oddeven/[n]`. This will name the number at the end of the URL as a Request parameter `n`.

In the new directory we create a Svelte page file (`+page.svelte`), that imports the function `isEven()`, extras the `n` property send by a server script, and creates an ondd or even message about the number as appropriate.

`/routes/oddeven/[n]/+page.svelte`

```javascript
<svelte:head>
  <title>-- oddeven/<n> --</title>
</svelte:head>

<script>
  import { isEven } from '$lib/util/useful_functions.js';

  let { data } = $props();
  let n = data.n;

  let message = n + ' is an ODD number';
  if(isEven(n)) {
  message = n + ' is an EVEN number';
}
</script>

<p>
  {message}
</p>
```


## Question 3a - Route with data `/oddeven`

In directory `/routes/oddeven` we need to create a Svelte page file (`+page.svelte`). This is a simple page that will output the error message about missing parameter:

`/routes/oddeven/+page.svelte`

```html
<svelte:head>
  <title>-- Odd Even - missing param --</title>
</svelte:head>

<h1>Error - missing parameter</h1>

<p>
  you have to provide a number at the end of the URL, e.g. /oddeven/6
</p>
```