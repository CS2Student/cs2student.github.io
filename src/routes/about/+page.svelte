<script>
	export let contactInfo = {
		email: 'aidenyhu@gmail.com'
	};

	export let education = {
		degree: 'Bachelor of Science in Computer Science and Mathematics',
		university: 'University of Maryland, College Park',
		graduationDate: 'May 2025'
	};

	export let courses = [
		'Object-Oriented Programming',
		'Discrete Mathematics',
		'Computer Systems',
		'Algorithms',
		'Organization of Programming Languages',
		'Data Science',
		'Advanced Data Structures'
	];

	export let experience = {
		position: 'Software Engineer',
		company: 'App Dev Club - General Dynamics Team',
		startDate: 'Jan. 2024',
		endDate: 'Present'
	};
</script>

<div class="container">
	<div class="section">
		<div class="section-header">Contact Information</div>
		<div class="section-content">
			<p>Email: {contactInfo.email}</p>
		</div>
	</div>

	<div class="section">
		<div class="section-header">Education</div>
		<div class="section-content">
			<p>Degree: {education.degree}</p>
			<p>University: {education.university}</p>
			<p>Graduation Date: {education.graduationDate}</p>
		</div>
	</div>

	<div class="section">
		<div class="section-header">Relevant Coursework</div>
		<div class="section-content">
			<ul class="courses-list">
				{#each courses as course}
					<li>- {course}</li>
				{/each}
			</ul>
		</div>
	</div>

	<div class="section">
		<div class="section-header">Experience</div>
		<div class="section-content">
			<p>Position: {experience.position} at {experience.company}</p>
			<p>Dates: {experience.startDate} - {experience.endDate}</p>
		</div>
	</div>
</div>

<style>
	.container {
		max-width: 800px;
		margin: 50px auto;
		padding: 20px;
		border: 1px solid #ccc;
		border-radius: 5px;
		background-color: #fffbcc;
		color: var(--text-1-light);
	}

	.section {
		margin-bottom: var(--size-fluid-2);
	}

	.section-header {
		font-size: var(--font-size-4);
		font-weight: bold;
		margin-bottom: var(--size-fluid-1);
	}

	.section-content {
		font-size: var(--font-size-1);
	}

	.courses-list {
		list-style-type: none;
		padding: 0;
	}
</style>
