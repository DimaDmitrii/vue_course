<script setup>
    import css from "./Card_template.module.css"
    import { ref, reactive } from "vue"
    css

    // props: ["<name>", "some teg information"]
    // const teg_name = ref ("<name>")
    // const teg_info = ref ("some teg information")

    // function change_teg_name (new_name) {
    //     teg_name.value = new_name
    // }

    // function change_teg_info (new_info) {
    //     teg_info.value = new_info
    // }

    // defineProps({
    //     modelValue: {
    //         type: string,
    //         // value: "<name>",
    //     }
    //     // teg_info: {
    //     //     type: string,
    //     //     // value: "some text",
    //     // }
    // })

    const teg = reactive ({
        name: "<name>",
        info: "some info text",
    })

</script>

<template>
    <div :class="css/content">
        <div :class="css.header">
            <h2>
                <div :class="css.teg_bar">teg  </div> {{ teg.name }} _
            </h2>
        </div>
        <div :class="css.content">
            <p>teg {{ teg.name }} <br/>{{ teg.info }}</p>
        </div>
    </div>
</template>