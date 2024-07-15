# NotPaid

This project is inspired by [kleampa/not-paid]('https://github.com/kleampa/not-paid').
I found the project interesting and funny and through this project I decided to publish my contribution made with SvelteKit!

## Installation & Usage

To install the package with npm run the following:
```bash
npm install not-paid-svelte
```

Then you can import the component with
```svelte
<script>
    import NotPaid from 'not-paid-svelte';
</script>
```

And use it like this:

```svelte
<NotPaid days_deadline={60} due_date={new Date('2024-06-5')} />
```

If you don't want the whole page to slowly fade away but just a small part, then you can do the following:
```svelte
<NotPaid days_deadline={60} due_date={new Date('2024-06-5')} global={false}>
    <h1>This will disappear</h1>
    <h1 slot="alt">This will appear</h1>
</NotPaid>
```

## Demo
You can see a live demo [here](https://sebaofficial.github.io/not-paid-svelte/).