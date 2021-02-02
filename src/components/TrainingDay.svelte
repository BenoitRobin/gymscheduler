<!-- Mon script -->

<script>
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

</style>
	
<!-- Mon code -->

<div>
    <form>
        <select bind:value={nbDaysTrainingsPerWeek}>
            {#each nbOfDays as day (day.id) }
                <option value={day}>{day.text} per week</option>
            {/each}
        </select>
    </form>
    {JSON.stringify(nbDaysTrainingsPerWeek)}
</div>