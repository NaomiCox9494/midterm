<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot></slot>
                <!--ToDo: Add default slot tag for passing the quote-->
            </div>
        </div>
    </div>
</template>

<script>
</script>

<style>

    .panel{
        font-family: Helvetica;
        font-size: large;
        color: deeppink;
    }
    /*ToDo: Create a class panel that sets the font-family to preffered font*/
        /*Set a specific front size to your liking*/
        /*Set a color of your choice*/
    .quote{
        cursor: pointer;
    }
    /*ToDo: Create a class quote that sets the cursor to a pointer*/
    .quote:hover{
        background-color: darkturquoise;
    }
    /*ToDo: Create a hover effect on the class quote changing the background color to a color you prefer*/
</style>