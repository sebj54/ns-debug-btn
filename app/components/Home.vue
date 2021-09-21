<template>
    <Page>
        <ActionBar>
            <Label text="Home"/>
        </ActionBar>

        <GridLayout>
            <StackLayout>
                <Label class="info">
                    <FormattedString>
                        <Span class="fas" text.decode="&#xf135; "/>
                        <Span :text="message"/>
                    </FormattedString>
                </Label>

                <Button
                    class="btn -primary"
                    text="Go to test page"
                    @tap="goToTestPage"
                />
            </StackLayout>
        </GridLayout>
    </Page>
</template>

<script>
import TestPage from './TestPage.vue'

export default {
    computed: {
        message() {
            return "Blank {N}-Vue app";
        }
    },
    methods: {
        goToTestPage() {
            this.$navigateTo(TestPage)
        },
    },
};
</script>

<style scoped lang="scss">
    @import '@nativescript/theme/scss/variables/blue';

    // Custom styles
    .fas {
        @include colorize($color: accent);
    }

    .info {
        font-size: 20;
        horizontal-align: center;
        vertical-align: center;
    }
</style>
