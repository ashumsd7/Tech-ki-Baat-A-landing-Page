<template>
    <div>
<p>{{timestamp}}</p>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                timestamp:''
            }
        },
        methods: {
            getNow(){
                 const today = new Date();
                   

                    let hoursLeft= Math.abs((today.getHours()))
                    let minsLeft= Math.abs(today.getMinutes() -59);
                    let secLeft= Math.abs(today.getSeconds()-59);

                    hoursLeft= hoursLeft<10 ? "0"+hoursLeft + "hrs "   : hoursLeft + "hrs"
                    minsLeft= minsLeft<10 ? "0"+minsLeft + "mins " : minsLeft + "mins"
                     secLeft= secLeft<10 ? "0"+secLeft + "secs " : secLeft + "secs"

    const time= hoursLeft + ": " + minsLeft + ": " + secLeft ;



                     const dateTime =time
                    this.timestamp = dateTime;
            }
        },
          created() {
                setInterval(this.getNow, 1000);
            },
    }
</script>

<style scoped>
p{font-weight: bolder;
color: rgb(14, 13, 15);
text-shadow: 2px 4px 10px rgb(255, 255, 255);
margin-top: 5px;}

</style>