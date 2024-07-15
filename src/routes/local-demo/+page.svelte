<script lang="ts">
    import { page } from '$app/stores';
    import NotPaid from '$lib/index.js';
</script>

<h1>Local Demo</h1>

<NotPaid global={false} due_date={new Date($page.url.searchParams.get('due_date'))} days_deadline={+$page.url.searchParams.get('days_deadline')}>
    <span>This element disappears</span>

    <span slot="alt">This element appears</span>
</NotPaid>