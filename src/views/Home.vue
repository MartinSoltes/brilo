<template>
	<Header/>
	<FormattedText
		v-for="textContent in texts"
		:key="textContent"
		:imgSrc="textContent.imgSrc"
		:imgPosition="textContent.imgPosition"
		:contentClasses="textContent.contentClasses"
		:class="textContent.wrapperClasses"
	>
		<div>
			<div v-html="textContent.content" class="formatedText-content"></div>
			<div v-if="textContent.buttons" class="button-group" :class="textContent.btnGroupClasses">
				<Button v-for="textButton in textContent.buttons" :key="textButton"
					:link="textButton.btnLink"
					:variant="textButton.variant"
					:active="textButton.active"
				>
					{{ textButton.btnText }}
				</Button>
			</div>
		</div>

	</FormattedText>

	<ArticleList :articles="articles" :articleFilters="articleFilters"/>
	<Footer/>
</template>

<script>
import ArticleList from '/src/components/articles/ArticleList.vue';
import Button from '/src/components/Button.vue';
import Footer from '/src/components/Footer.vue';
import FormattedText from '/src/components/FormattedText.vue';
import Header from '/src/components/Header.vue';



export default {
    name: 'Home',
    components: { ArticleList, Button, FormattedText, Footer, Header },
	data() {
		return {
			texts: [
				{
					content: "<h1>Hlavní nadpis webu</h1><p>V k žert planetu rysů obdivují stravování starověkého zebřičky u&nbsp;tahů zimující. Akcí a&nbsp;důkaz pomoci narozen muzea signálem.</p>",
					wrapperClasses: "pb-64 u-md-pb-112",
					contentClasses: "d-flex align-items-center text-center text-lg-start mx-auto mx-lg-0",
					btnGroupClasses: "justify-content-md-center justify-content-lg-start",
					imgSrc: "/images/text-img-1.jpg",
					imgPosition: "right",
					buttons: [
						{
							btnText: "Více informací",
							btnLink: "#",
							variant: "secondary"
						},
						{
							btnText: "Poptat nabídku",
							btnLink: "#",
							variant: "primary"
						}
					]
				},
				{
					content: "<h2>Nechte své peníze růst!</h2><p>V k žert planetu rysů obdivují stravování starověkého zebřičky u&nbsp;tahů zimující. Akcí a&nbsp;důkaz pomoci narozen muzea signálem – jižní využitelný uchu těžko. Dravcům vousům houba horu žijí mého vývojovou z společnosti nemigrují vy plná internetová, je charisma vnitrozemí, oceán a přijíždějí příbuzných zjevné, zemskou dá spolu. Moc král prokletí obyvatel holka ochlazení žít mimořádnými virů stejný či palec.</p><ul><li>Musel za až angličtinu látky nohy deprimovaná polokouli i roku map.</li><li>Těžko popsal, ještě zúročovat však, by čase musel mi nuly, ta naší</li><li>Musel za až angličtinu látky nohy deprimovaná polokouli i roku map.</li><li>Těžko popsal, ještě zúročovat však, by čase musel mi nuly, ta naší</li></ul>",
					wrapperClasses: "bg-light-blue pb-64 pt-64 u-md-pb-112 u-md-pt-112",
					imgSrc: "/images/text-img-2.jpg",
					imgPosition: "left",
					buttons: [
						{
							btnText: "Zjistit více",
							btnLink: "#",
							variant: "primary"
						}
					]
				},
				{
					content: "<h2>Nechte své peníze růst!</h2><p>V k žert planetu rysů obdivují stravování starověkého zebřičky u&nbsp;tahů zimující. Akcí a&nbsp;důkaz pomoci narozen muzea signálem – jižní využitelný uchu těžko. Dravcům vousům houba horu žijí mého vývojovou z společnosti nemigrují vy plná internetová, je charisma vnitrozemí, oceán a přijíždějí příbuzných zjevné, zemskou dá spolu. Moc král prokletí obyvatel holka ochlazení žít mimořádnými virů stejný či palec.</p>",
					wrapperClasses: "pb-64 pt-64 u-md-pb-112 u-md-pt-112",
					imgSrc: "/images/text-img-3.jpg",
					imgPosition: "right",
					buttons: [
						{
							btnText: "Zaregistovat se",
							btnLink: "#",
							variant: "primary"
						}
					]
				},

			],
			articles: [
				{
					title: "Látkové tašky s potiskem",
					annotation: "Dlouhá význam s sionismu ty, jí antény i sezona, bílá malých izolovány uvést masové vodě",
					img: "/images/article-img-1.jpg",
					curl: "#",
					category: "canvas"
				},
				{
					title: "Látkové tašky bez potisku",
					annotation: "Dlouhá význam s sionismu ty, jí antény i sezona",
					img: "/images/article-img-2.jpg",
					curl: "#",
					category: "canvas"
				},
				{
					title: "Bílé papírové tašky",
					annotation: "Dlouhá význam s sionismu ty, jí antény i sezona, bílá malých izolovány uvést masové vodě",
					img: "/images/article-img-3.jpg",
					curl: "#",
					category: "paper"
				},
				{
					title: "Barevné papírové tašky na dárky",
					annotation: "Dlouhá význam s sionismu ty, jí antény i sezona, bílá malých izolovány uvést masové vodě",
					img: "/images/article-img-4.jpg",
					curl: "#",
					category: "paper"
				},
				{
					title: "Papírové tašky z recyklovatelného materiálu",
					img: "/images/article-img-1.jpg",
					annotation: "Dlouhá význam s sionismu ty, jí antény i sezona, bílá malých izolovány uvést masové vodě",
					curl: "#",
					category: "paper"
				},
				{
					title: "Igelitové sáčky s logem",
					annotation: "Dlouhá význam s sionismu ty, jí antény i sezona, bílá malých izolovány uvést masové vodě",
					img: "/images/article-img-2.jpg",
					curl: "#",
					category: "plastic"
				},
				{
					title: "Velké igelitové tašky s potiskem",
					annotation: "Dlouhá význam s sionismu ty, jí antény i sezona, bílá malých izolovány uvést masové vodě",
					img: "/images/article-img-3.jpg",
					curl: "#",
					category: "plastic"
				},

			],
			articleFilters: {
				content: '<h2 class="pb-2">Vyberte jednu z nabízených služeb</h2><p>Hlasu zkrátka nevratné duší indičtí půlkilometrová začali nutné už od středisko. Společných snažila líně budoucnost začne vloženy stal objevováním, umělé cílem starým dne větvičky názvy moři zabíjí.</p>',
				wrapperClasses: "",
				filters: [
					{
						label: "všechno",
						value: '',
					},
					{
						label: "Papírové tašky",
						value: "paper",
					},
					{
						label: "látkové tašky",
						value: "canvas",
					},
					{
						label: "Igelitové tašky",
						value: "plastic",
					}
				]
			},
		}
	}
}
</script>

<style>

</style>