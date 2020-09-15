<template>
    <form>
        <div>
            <b-form-textarea
                class="textarea-state"
                v-model="quote"
                :state="quote.length >= 7"
                placeholder="Enter at least 7 characters"
                rows="3"
            ></b-form-textarea>
        </div>

        <b-button 
            variant="success" 
            class="button" size="lg" 
            @click.prevent="createNew"
            style="box-shadow: none"
            :style= "[quote.length >= 7 ? {'background': '#4cd137', 'border': 'none', 'outline':'none'} : {'background': '#e84118', 'border': 'none', 'outline':'none'}]"
        >
                ADD QUOUTE
        </b-button>
    </form>
</template>

<script>

export default {
    data: function() {
        return {
            quote: ''
        }
    },
    methods: {
        createNew() {
            if (this.quote.length >= 7) {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
}
</script>

<style>
.textarea-state {
    margin-top: 20px;
}

.button {
    margin-top: 20px;
    transition: 0.4s;
}

.textarea-state {
    margin-top: 40px;
}


</style>