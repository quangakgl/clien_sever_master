<template>
    <div id="app">
        <select v-model="selected" name="selectOpt" v-on:change="getList()">
            <option v-for="item in selectItems" :value="item.type">{{ item.name }}</option>
        </select>
        <div>
            <p>Selected: {{selected}}</p>
            <images :images="things"></images>
        </div>
    </div>
</template>
<script>
	export default {
		data() {
			return {
				selected: 0,
				things: [],
				errorMsg: ''
			}
		},

		methods: {
			getList() {
				axios.post('/querydata', {
					selectedType: this.selected
				}).then(response => {
					console.log(response)
					this.things = response.data
				}).catch(error => {
					this.errorMsg = 'No user or no location'
					this.things = []
				})
			}
		}
	}
</script>