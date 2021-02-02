<!-- Mon script -->
<script>
    export let title;
    let exercice = {
        activity: "",
        sets: 4,
        reps: 10,
    }

    let exercices = [];

    function handleSubmit() {
        exercices= [...exercices, {...exercice }];
        console.log('exercices :', exercices);
    }


</script>

<!-- Mon style -->

<style type="text/scss">

</style>
	
<!-- Mon code -->

<div class="container">
    <h2>{title}</h2>
    <div>
        <form on:submit|preventDefault={handleSubmit}>
            <div>
                <label for="activity">Activity</label>
                <input type="text" id="activity" bind:value={exercice.activity}>
            </div>
            <div>
                <label for="sets">Sets</label>
                <input type="number" id="sets" bind:value={exercice.sets}>
            </div>
            <div>
                <label for="reps">Reps</label>
                <input type="number" id="reps" bind:value={exercice.reps}>
            </div>
            <button type="submit">add exercice</button>
        </form>
    </div>
</div>