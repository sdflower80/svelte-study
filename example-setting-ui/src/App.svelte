<script>

    import ConfigureDivList from "./ConfigureDivList.svelte";

    let configureList = [];

    const addConfigure = (key, desc, value) => {
        configureList.push({
                key: key,
                desc: desc,
                value: value
            });
    };

    addConfigure("TEST_KEY_TEXT_VALUE", "TEXT", "TEST_VALUE");
    addConfigure("TEST_KEY_BOOLEAN_VALUE", "BOOLEAN", "TEST_VALUE");
    addConfigure("TEST_KEY_LONG_STRING_VALUE", "LONG_STRING", "TEST_VALUE");
    addConfigure("TEST_KEY_JSON_VALUE", "JSON", "{\"k\":\"value\"}");
</script>

<main>
    <h1>Setting UI</h1>

    <ConfigureDivList configureList={configureList} />

</main>

<style>

</style>