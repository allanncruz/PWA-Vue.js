<template>
    <section>
        <h1 class="m-5">Permissões</h1>

        <a href="" @click.prevent="readPermission()">Ler Permissão</a>

        <p>{{ permissionStatus }}</p>
    </section>
</template>

<script>
    export default {
        data() {
            return {
                permissionStatus: null
            }
        },
        methods: {
            readPermission() {
                let permission = navigator.permissions.query({
                    // name: 'geolocation'
                    // name: 'notifications'
                    // name: 'midi'
                    name: 'push',
                    userVisibleOnly: true
                })
                permission.then((response) => {
                    this.permissionStatus  = response.state
                    console.log(response)
                })
            }
        }
    }
</script>