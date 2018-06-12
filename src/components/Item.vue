<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body item">
                <slot></slot>
            </div>
        </div>

    </div>
</template>

<script>

</script>

<style>

.panel-body{
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    font-size: 24px;
    color: #6e6e6e;
}
.item{
    cursor: pointer;
}

.item:hover{
    background-color: #ffe2e2;
}

</style>


