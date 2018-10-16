<template>
    <div class="container">
        <!--ToDo: Use the Header component selector-->
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
            <!--Bind data props quoteCount and set it equal to the quote length-->
            <!--Bind data props maxQuotes and set it equal to the maxQuotes created below-->

        <!--ToDo: Use the NewQuote component selector-->
        <app-new @quoteAdded = "newQuote"></app-new>
            <!--Initiate an $emit event listener called quoteAdded that is equal to newQuote-->

        <app-quoteGrid :quotes="quotes" @quoteDeleted = "deleteQuote"></app-quoteGrid>
        <!--ToDo: Use the QuoteGrid component selector-->
            <!--Bind data props quotes and set it equal to the quotes array created below-->
            <!--Call quoteDeleted that is emitted from the QuoteGrid Component and pass the deleteQuote method created below-->
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>

    import NewQuote from './components/NewQuote.vue';
    import QuoteGrid from './components/QuoteGrid.vue';
    import Header from './components/Header.vue';
//  Todo: Import QuoteGrid, NewQuote, and Header Components

    export default {
        data: function () {
            return {

                quotes: ['You are a wizard, Harry -Hodor'],
                // ToDo: Create an array data object called quotes
                    // Have at least one string quote by default
                maxQuotes: 10
                // ToDo: Create a data object maxQuotes that is set to 10
            }
        },
        methods: {

            newQuote(quote){
              if(this.quotes.length >= this.maxQuotes){
                alert("Please delete Quotes first!! ")
              }else{
                this.quotes.push(quote);
              }

            },

            deleteQuote(index){
                this.quotes.splice(index,1)
            }
            // ToDo: Create a method that checks when a newQuote is created and takes the parameter quote.
                // This method will check if the quotes (Array Data Object) length is greater than or equal to the max quotes allowed
                // If it is return an alert telling the user to delete a quote
                // Outside of conditional, push quote (method parameter) to the quotes array

            // ToDo: Create a method deleteQuote that takes in a parameter of index
                // This method will splice the quotes array by (index, 1)
        },
        components: {

            'app-new' : NewQuote,
            'app-quoteGrid' : QuoteGrid,
            'app-header' : Header
            // ToDo: Initiate the QuoteGrid, NewQuote, and Header Components with Custom Selectors
        }
        
    }
</script>

<style>
</style>
