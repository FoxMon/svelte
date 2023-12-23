<script>
    const formValues = {
        title: {
            type: "text",
            value: "",
        },
        contents: {
            type: "text",
            value: "",
        }
    };

    let isOpenDialog = false;

    function onInputChangeEvent(e) {
        const { name, value } = e.target;

        formValues[name].value = value;
    }

    function onDialogButtonClickEvent() {
        isOpenDialog = !isOpenDialog;
    }
</script>

<div>
    <h1>Form</h1>

    {#each Object.keys(formValues) as key}
        <div>
            <input 
                type={formValues[key].type} 
                name={key} 
                value={formValues[key].value}
                on:input={onInputChangeEvent} 
            />
        </div>
    {/each}

    <button on:click={onDialogButtonClickEvent}>Show</button>

    <dialog open={isOpenDialog}>
        <h3>{formValues.title.value}</h3>
        <p>{formValues.contents.value}</p>

        <form method="dialog" on:submit={onDialogButtonClickEvent}>
            <button>Close</button>
        </form>
    </dialog>
</div>