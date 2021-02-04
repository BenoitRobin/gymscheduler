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

.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: start;
    font-family: 'Roboto Mono', sans-serif;

    &-title {
        text-transform: uppercase;
    }

    &-form {
        margin: auto;

        &--item {
            display: flex;
            flex-direction: column;
            align-items: flex-end;
        }

        &--btn {
            border-radius: 5px;
            background-color: #d4e3eb;
            margin-top: 1.5em;
            padding: .5em 1em;
            transition: padding .5s, background-color .5s;
        }

        &--btn:hover {
            color: #fff;
            background-color:#000;
            padding: .5em 3em;
        }
    }
}

input {
    background-color: #d4e3eb;
    border-radius: 5px;
    margin-top: .5em
}

</style>
	
<!-- Mon code -->

<div class="container">
    <h2 class="container-title">{title}</h2>
    <div class="container-form">
        <form on:submit|preventDefault={handleSubmit}>
            <div class="container-form--item">
                <label for="activity">Activity</label>
                <input type="text" id="activity" bind:value={exercice.activity}>
            </div>
            <div class="container-form--item">
                <label for="sets">Sets</label>
                <input type="number" id="sets" bind:value={exercice.sets}>
            </div>
            <div class="container-form--item">
                <label for="reps">Reps</label>
                <input type="number" id="reps" bind:value={exercice.reps}>
            </div>
            <button class="container-form--btn"type="submit">add exercice</button>
        </form>
    </div>
</div>