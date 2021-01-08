<template>
	<v-app id="app">
		<v-container class="col-lg-5 col-md-8">
			<v-card class="d-flex">
				<v-col class="col-5 left red darken-4 white--text pa-0">
					<v-img :src="img" max-height="400" />
					<div class="pa-5">
						<v-card-title class="font-weight-bold">Contacts</v-card-title>
						<div class="d-flex flex-column">
							<p><v-icon class="mr-2">mdi-cellphone</v-icon> 06 50 84 95 71</p>
							<p>
								<v-icon class="mr-2">mdi-mail</v-icon>
								monadresse@gmail.com
							</p>
							<p><v-icon class="mr-2">mdi-home</v-icon> 5 rue de la liberté Paris</p>
							<p><v-icon class="mr-2">mdi-email</v-icon> 75400</p>
						</div>
						<v-card-title class="font-weight-bold">A propos de moi</v-card-title>
						<p class="px-7 about-me">
							20 ans, passionné depuis mon
							plus jeune âge par
							l’informatique, il était évident
							que j’en fasse mon métier.<br><br>

							Actuellement apprenti chez EDF
							en tant qu'analyste-
							développeur, ces deux années
							m’ont permis de valider mon
							choix et de découvrir le métier
							d’ingénieur dans mes relations
							avec mon maître d'apprentissage.<br><br>

							Mon souhait est d’élargir mes
							compétences ainsi que mes
							connaissances pour devenir
							ingénieur en informatique.
						</p>
					</div>
				</v-col>
				<v-col class="col-7 right-content">
					<div class="pb-5 name-job">
						<h1 class="text-center red--text text--darken-4">
							Maxime Consigny
						</h1>
						<h3 class="text-center">Alternant analyste métier</h3>
					</div>
					<v-card-title class="red--text text--darken-4 font-weight-bold"
						>COMPÉTENCES</v-card-title
					>
					<h3 class="mb-3">Savoir faire</h3>
					<ul>
						<li v-for="item in items" :key="item">{{ item }}</li>
					</ul>
					<div class="languages d-flex my-5">
						<div class="col-5 pt-0">
							<h4 class="mb-3">Langues</h4>
							<p class="mb-0">Anglais</p>
							<p class="mb-0">Espagnol</p>
						</div>
						<div class="d-flex align-center">
							<p>
								Plusieurs séjours en famille d'accueil dans des pays anglophones (Norvège, Angleterre et Etats-Unis)
							</p>
						</div>
					</div>
					<div class="languages-info d-flex mt-5">
						<div class="col-4">
							<h4 class="mb-3">Langues Info</h4>
							<p>Appris à l'Iut et en entreprise</p>
						</div>
						<div class="d-flex align-center flex-column col-8">
							<div
								v-for="languages in languagesIt"
								:key="languages.name"
								class="d-flex"
							>
								<p class="col-5 ma-0">{{ languages.name }}</p>
								<v-rating
									class="d-flex"
									v-model="languages.note"
									dense
									color="#B71C1C"
									background-color="grey-light"
									half-increments
									readonly
								/>
							</div>
						</div>
					</div>
					<v-card-title class="red--text text--darken-4 font-weight-bold"
						>FORMATIONS</v-card-title
					>
					<div class="formation d-flex">
						<div class="col-4">
							<h4 class="mb-3">IUT Informatique apprentissage</h4>
							<p>Societe EDF</p>
						</div>
						<div class="col-8">
							<v-card-subtitle class="pt-0">Projet à EDF</v-card-subtitle>
							<ul>
								<li>
									Développement d'un outil de visualisation de charge de travail.
								</li>
								<li>
									Gestion d'un groupe de développeurs (gestion de projet encadré par mon tuteur).
								</li>
							</ul>
						</div>
					</div>

					<div class="d-flex">
						<div class="col-4">
							<h4 class="mb-3">BacS, sciences de l'ingénieur</h4>
							<p>Mention assez bien</p>
						</div>
						<div class="col-8">
							<v-card-subtitle class="pt-0"
								>Principales notes du bac</v-card-subtitle
							>
							<ul>
								<li v-for="note in notes" :key="note">{{ note }}</li>
							</ul>
						</div>
					</div>
					<v-card-title class="red--text text--darken-4 font-weight-bold"
						>CENTRES D’INTÉRÊT</v-card-title
					>
					<ul>
						<li v-for="interet in interets" :key="interet">{{ interet }}</li>
					</ul>
				</v-col>
			</v-card>
		</v-container>
	</v-app>
</template>

<script>
export default {
	name: "App",
	data() {
		return {
			img: require("./assets/IMG_1190.jpeg"),
			items: [
				"Analyse de besoin, définition et rédaction du cahier des charges.",
				"Planification de projet (Gantt, méthode Agile/Scrum) avec détermination des besoins matériels et humains.",
				"Rédaction de spécifications techniques.",
				"Conception et développement d'applications informatiques.",
				"Communication (Eloquence), animation de réunions."
			],
			languagesIt: [
				{
					name: "Python",
					note: 4
				},
				{
					name: "Java",
					note: 3.5
				},
				{
					name: "SQL",
					note: 4
				},
				{
					name: "Web",
					note: 2.5
				}
			],
			notes: [
				"Mathématiques: 16",
				"Anglais: 17",
				"Anglais Euro / Maths Euro: 17",
				"Physique Chimie: 13"
			],
			interets: ["Sports", "Guitare", "Aviron", "Veilles de technologies"]
		};
	}
};
</script>

<style lang="scss" scoped>
@import "./style/variables";
.left {
	box-shadow: 5px 0 5px -5px #333;
	.about-me {
		line-height: 1.8em;
	}
}
.right-content {
	.name-job {
		border-bottom: 2px #b71c1c solid;
	}
}
</style>