<script lang="ts">
	interface Chapter {
		number: number;
		title: string;
		strapline: string;
		excerpt: string;
	}

	const chapters: Chapter[] = [
		{
			number: 1,
			title: 'Navigating the Canadian Bureaucracy',
			strapline: 'Understanding Visas, Residency, and Legal Essentials',
			excerpt:
				"Moving to Canada involves navigating a complex system of immigration and residency processes. This chapter breaks down the essential steps needed to secure your visa, establish residency, and handle other legal formalities. Whether you're planning a short-term stay or aiming for permanent residency, understanding Canada's legal framework is crucial. We'll explore various visa options, such as work and study permits, and provide tips on streamlining the application process. Additionally, this chapter covers essential documentation, like obtaining a Social Insurance Number (SIN), which is key to accessing many services. We'll also delve into registering with your province or territory and understanding Canadian tax implications. Whether you're relocating for work, study, or lifestyle, this chapter provides practical advice and insider tips to ensure you're legally prepared for your new life in Canada."
		},
		{
			number: 2,
			title: 'Finding Your Dream Home in Canada',
			strapline: 'From Urban High-Rises to Rural Retreats: Where and How to Live',
			excerpt: `
    Canada offers a diverse range of living options, from bustling city neighborhoods to scenic countryside. This chapter is your guide to finding the perfect home that suits your lifestyle and budget. We'll start by exploring popular regions for newcomers, highlighting the unique qualities of each. Whether you're drawn to the urban energy of Toronto and Vancouver, the affordable charm of the Prairies, or the natural beauty of Atlantic Canada, understanding the local real estate market is key. We'll discuss the pros and cons of renting versus buying, and provide practical advice on navigating the Canadian housing market. You'll learn about different property types, from modern condos to suburban homes, and the steps involved in securing a lease or purchase. We'll also cover important considerations such as proximity to amenities, transportation, and local schools. This chapter equips you with the knowledge to make an informed decision, ensuring your new Canadian home meets all your expectations.`
		},
		{
			number: 3,
			title: 'Mastering the Canadian Job Market',
			strapline: 'Strategies for Employment and Freelancing in a New Culture',
			excerpt: `Finding a job in Canada can be a challenging but rewarding experience, especially if you're unfamiliar with the local job market and work culture. This chapter provides an overview of the Canadian employment landscape, offering strategies to help you secure a job or establish a successful freelance career. We'll examine sectors with the most opportunities for newcomers, such as technology, healthcare, finance, and skilled trades. You'll learn how to tailor your resume to meet Canadian expectations and network effectively in a culture that values professionalism. For those interested in freelancing, we'll explore the requirements for self-employment, including tax obligations and social benefits. Additionally, we'll discuss the importance of language skills and credential recognition to enhance job prospects. Whether you're looking to climb the corporate ladder, start a business, or work remotely, this chapter offers valuable insights to help you navigate the Canadian job market successfully.`
		},
		{
			number: 4,
			title: 'Embracing the Canadian Lifestyle',
			strapline: 'Cultural Norms, Social Etiquette, and Building Connections',
			excerpt: `Moving to Canada isn't just about changing your location; it's about embracing a new way of life. This chapter explores the Canadian lifestyle, offering insights into cultural norms, social etiquette, and making meaningful connections. We'll begin by discussing the importance of community and inclusivity in Canada, where people are known for politeness and respect for diversity. You'll learn about Canada's distinct seasons, holiday traditions, and the concept of work-life balance. We'll also delve into social etiquette, from greetings to navigating Canadian dining customs. Whether you're joining a hockey game, attending local events, or enjoying nature, understanding these cultural nuances will help you integrate smoothly. Additionally, we'll offer tips on building a social network, whether through community centers, newcomer groups, or local clubs. By the end of this chapter, you'll be well-prepared to embrace Canada's friendly, inclusive, and outdoor-oriented lifestyle.`
		},
		{
			number: 5,
			title: 'Budgeting and Finances in Canada',
			strapline: 'Managing Costs, Taxes, and Banking in Your New Home',
			excerpt: `Successfully managing your finances is key to enjoying a comfortable life in Canada. This chapter provides practical guidance on budgeting, managing expenses, and navigating Canada's financial systems. We'll start by discussing the cost of living across different regions, from the high costs in major cities like Toronto to more affordable options in smaller towns. You'll learn how to create a realistic budget covering essentials such as housing, utilities, groceries, and healthcare. We'll also explain Canada's banking system, offering tips on opening a bank account, understanding credit scores, and choosing financial products. Taxation is another key area, with guidance on filing taxes as a resident or non-resident, as well as understanding Canada's tax treaties with other countries. Whether you're planning to work, study, or retire, this chapter equips you with financial knowledge to make the most of your resources and enjoy a stable life in your new home.`
		}
	];

	let selectedChapterNumber = $state(1);
	let selectedChapter = $derived(
		chapters.find((chapter) => chapter.number === selectedChapterNumber)
	);

	const selectChapter = (chapter: Chapter) => {
		selectedChapterNumber = chapter.number;
	};
</script>

<section class="landing-page-section">
	<h2 class="mb-l">What you're getting</h2>
	<div class="chapter-container">
		<ul>
			{#each chapters as chapter}
				<li>
					<button
						class="chapter-title"
						class:selected-chapter-title={selectedChapterNumber === chapter.number}
						aria-controls={`chapter-info-${chapter.number}`}
						aria-expanded={selectedChapterNumber === chapter.number}
						onclick={() => selectChapter(chapter)}
					>
						<h3>Chapter {chapter.number}: {chapter.title}</h3>
					</button>
				</li>
			{/each}
		</ul>
		<div class="chapter-info">
			<h3 class="chapter-strapline italic mb-s">
				{selectedChapter?.title}
			</h3>
			<p>
				{selectedChapter?.excerpt}
			</p>
		</div>
	</div>
</section>

<style>
	.chapter-container {
		display: flex;
		justify-content: space-between;
	}

	.chapter-container ul {
		width: 40%;
	}

	.chapter-info {
		width: 55%;
	}

	.chapter-title {
		border-bottom: 1px solid grey;
		width: 100%;
		display: block;
		padding: 12px;
		text-align: left;
	}

	.selected-chapter-title {
		background-color: black;
		border: none;
		color: white;
		box-shadow:
			0 4px 6px rgba(0, 0, 0, 0.1),
			0 1px 3px rgba(0, 0, 0, 0.08);
	}
</style>
