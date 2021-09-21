<template>
    <Page>
        <ActionBar>
            <Label text="Test page"/>
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
                    text="Do the test"
                    @tap="doTheTest"
                />

                <Label class="info" :text="isWorking ? '✅ tap is working' : '❌ tap is not working'" />

                <Button
                    class="btn -secondary"
                    text="Go back"
                    @tap="goBack"
                />
            </StackLayout>
        </GridLayout>
    </Page>
</template>

<script>
export default {
    data() {
        return {
            isWorking: null,
        }
    },
    computed: {
        message() {
            return "Blank {N}-Vue app";
        }
    },
    methods: {
        doTheTest() {
            this.isWorking = true
        },
        goBack() {
            this.$navigateBack()
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
