<a href="">Hover me</a>
<style>
    a{
        text-decoration: none;
        color: #272727;
        font-family: sans-serif;
        font-size: 45px;
        border: 5px solid #272727;
        padding: 40px 80px;
        position: relative;

        overflow: hidden;
    }
    a:before{
        transform-origin: bottom left;
        content: '';
        position: absolute;
        left: 0;
        top: 0;
        height: 100%;
        width:100%;
        transform: rotate(-90deg);
        background-color: #fff200;
        z-index: -1;
        transition: transform 1s;
  
    }
    a:hover:before{
        transform: rotate(0);
    }
</style>