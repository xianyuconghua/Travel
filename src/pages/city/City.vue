<template>
	<div>
		<city-header></city-header>
		<city-search :cities="cities"></city-search>
		<city-list 
			:cities="cities" 
			:hot="hotCities" 
			:letter="letter">				
		</city-list>
		<city-alphabet :cities="cities" @change="LetterChange"></city-alphabet>
	</div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
	name: 'City',
	components: {
		CityHeader,
		CitySearch,
		CityList,
		CityAlphabet
	},
	data() {
		return {
			hotCities: [],
			cities: {},
			letter:	''
		}
	},
	methods: {
		getCityInfo () {
			axios.get('/api/city.json')
			.then(this.getCityInfoSucc)
		},
		getCityInfoSucc (res) {
			//console.log(res)
			res = res.data
			if (res.ret && res.data) {
				const data = res.data				
				this.hotCities = data.hotCities
				this.cities = data.cities
			}
		},
		LetterChange(letter) {
			//console.log(letter)
			this.letter = letter
		}
	},
	mounted () {
		this.getCityInfo()
	}
}
</script>

<style scoped>
	
</style>