<!-- Mon script -->

<script>

    import TrainingDayDetails from './TrainingDayDetails.svelte';

	const nbOfDays = [
        {id: 1, text:'One day', value:[1]},
        {id: 2, text:'Two days', value:[1, 2]},
        {id: 3, text:'Three days', value:[1, 2, 3]},
        {id: 4, text:'Four days', value:[1, 2, 3, 4]},
        {id: 5, text:'Five days', value:[1, 2, 3, 4, 5]},
        {id: 6, text:'Six days', value:[1, 2, 3, 4, 5, 6]},
        {id: 7, text:'Seven days', value:[1, 2, 3, 4, 5, 6, 7]},
    ];

    let nbDaysTrainingsPerWeek;
</script>

<!-- Mon style -->

<style type="text/scss">

.container {
    width: 70%;
    background: #d4e3eb;
    margin: auto;
    padding: 2em;
    border: 1px solid #bde0ff;
    border-radius: 10px;

    display: flex;
    flex-direction: column;

    &-bloc1 {
        width: 25%;
        margin: auto;
    }

    &-bloc2 {
        margin-top: 2em;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-around;

        &--item {
            width: 25%;
            padding: .5em;
            margin-bottom: 1em;
            border: 1px solid #dcdcdc;
            border-radius: 10px;
            box-shadow: 3px 3px 3px #243A62;
            background-color: #bde0ff;
        }
    }
}

select {
    border-radius: 5px;
    margin-top: .5em
}
</style>
	
<!-- Mon code -->
<section class="container">
    <div class="container-bloc1">
        <form>
            <select bind:value={nbDaysTrainingsPerWeek}>
                {#each nbOfDays as day (day.id) }
                    <option value={day}>{day.text} per week</option>
                {/each}
            </select>
        </form>
        {JSON.stringify(nbDaysTrainingsPerWeek)}
    </div>

    {#if nbDaysTrainingsPerWeek}
    <div class="container-bloc2">
        {#each nbDaysTrainingsPerWeek.value as dayNumber, i }
            <div class="container-bloc2--item">
                <TrainingDayDetails title={`day ${++i}`}/>
            </div>
        {/each}
    </div>
    {/if}
</section>