<template>
    <Page actionBarHidden="true">

        <GridLayout>
            <Label class="m-10 h3" :text="item.description" verticalAlignment="top" ></Label>
             <Button text="Go to items" @tap="onButtonTap"/>
        </GridLayout>
    </Page>
</template>

<script>
import Items from "./Items";

export default {
    props: ["context"],

    computed: {
        item() {
            return this.context || {};
        }
    },
    methods: {
        onButtonTap () {           
            console.log('item tapped')
            this.$navigateTo(Items, {
                  frame: "itemContent",
                   clearHistory: false,
                props: { 
                    
                    animated: true,
                    transition: {
                        name: "slide",
                        duration: 200,
                        curve: "ease"
                    }}});
        }
    }
};
</script>

<style scoped lang="scss">
// Start custom common variables
@import "~@nativescript/theme/scss/variables/blue";
// End custom common variables

// Custom styles

</style>