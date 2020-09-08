# @amiceli/vue-socket.io-extended

This project is a fork of [vue-socket.io-extended](https://github.com/probil/vue-socket.io-extended).

Currenlty it added **event mapping** feature. My PR is still waiting so I publish my own version.

## install

    npm install @amiceli/vue-socket.io-extended -S

## event mapping

A socket io event example

~~~js
{ name : 'event', data : { task : 'synchronize', progress : 90 } }
~~~

Map event name to task data : 

~~~js
const options = {
    eventMapping : (eventName, args) => {
        const data = args[0]

        return data.task
    }
}
~~~

An use it in your component : 

~~~js
Vue.use(VueSocketIOExt, socket, options);

export default {
    sockets : {
        synchronize () {
            console.log ('progress received')
        }
    }
}
~~~