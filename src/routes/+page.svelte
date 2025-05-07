<script lang="js">
	import oldPort from '../assets/old_portfolio.png';
	import algoAnimate from '../assets/algo_animate.png';
	import pong from '../assets/pong.png';
	import tictactoe from '../assets/tictactoe.png';
	// skills
	import css from '../assets/skills/CSS3_logo_and_wordmark.svg.png';
	import html from '../assets/skills/HTML-5-Badge-Logo.png';
	import js from '../assets/skills/JavaScript-logo.png';
	import python from '../assets/skills/Python-logo-notext.svg.png';
	import react from '../assets/skills/images.png';
	import svelte from '../assets/skills/download.png';
	import tailwind from '../assets/skills/30317862.png';
	import typescript from '../assets/skills/Typescript.svg.png';
	import vercel from '../assets/skills/vercel-icon-512x449-3422jidz.png';
	import vite from '../assets/skills/images.jpeg';
	import github from '../assets/skills/GitHub-Mark-ea2971cee799.png';
	import git from '../assets/skills/Git-Icon-1788C.png';
	import node from '../assets/skills/images (1).png';

	let projects = [
		{
			name: 'Old Portfolio Webiste',
			imageURL: oldPort,
			description:
				'A portfolio website built using SvelteKit and TailwindCSS. You are currently viewing it!',
			link: 'https://port24-wheat.vercel.app/',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript', 'Vite', 'Vercel']
		},
		{
			name: 'Ping Pong Game',
			imageURL: pong,
			description:
				'A simple ping pong game built using HTML, CSS, and JavaScript in SvelteKit with TailwindCSS. The game features a two-player mode.',
			link: 'https://pong-v2-six.vercel.app/',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript', 'Vite', 'Vercel']
		},
		{
			name: 'TicTacToe Game',
			imageURL: tictactoe,
			description:
				'A simple TicTacToe game built using HTML, CSS, and JavaScript in SvelteKit with TailwindCSS. The game features a two-player mode and a color theme toggle.',
			link: 'https://tictactoe-v2.vercel.app/',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript', 'Vite', 'Vercel']
		},
		{
			name: 'Current Portfolio Webiste',
			description:
				'A portfolio website built using SvelteKit and TailwindCSS. You are currently viewing it!',
			link: 'https://weather-app-2-0.vercel.app/',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript', 'Vite', 'Vercel']
		},
		{
			name: 'Algorithm Visualizer',
			imageURL: algoAnimate,
			description:
				'A web application that visually demonstrates how algorithms work through step-by-step animations, helping users understand concepts like sorting and searching in an interactive and intuitive way.',
			link: 'https://algo-animate.vercel.app/',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript', 'Vite', 'Vercel']
		}
	];

	let languages = [
		{
			name: 'JavaScript',
			imageURL: js
		},
		{
			name: 'Python',
			imageURL: python
		},
		{
			name: 'HTML5',
			imageURL: html
		},
		{
			name: 'Typescript',
			imageURL: typescript
		},
		{
			name: 'CSS3',
			imageURL: css
		}
	];

	let libraries = [
		{
			name: 'React',
			imageURL: react
		},
		{
			name: 'TailwindCSS',
			imageURL: tailwind
		},
		{
			name: 'Node.js',
			imageURL: node
		},
		{
			name: 'Svelte',
			imageURL: svelte
		},
		{
			name: 'Vite',
			imageURL: vite
		}
	];

	let tools = [
		{
			name: 'Git',
			imageURL: git
		},
		{
			name: 'GitHub',
			imageURL: github
		},
		{
			name: 'Vercel',
			imageURL: vercel
		}
	];

	let email = $state('');
	let message = $state('');
	let subject = $state('');

	const handleEmail = (e) => {
		const mail = e.target.name;
		email = mail;
	};

	const handleSubject = (e) => {
		const sub = e.target.name;
		const newSub = sub.replace(/ /g, '%20');
		subject = newSub;
	};

	const handleMessage = (e) => {
		const msg = e.target.name;
		const newMsg = msg.replace(/ /g, '%20');
		message = newMsg;
	};
</script>

<section id="home" class="hero min-h-screen">
	<div class="hero-content text-center">
		<div class="max-w-md">
			<h1 class="text text-5xl font-bold">Jaedon Smith</h1>
			<p class=" py-6 text-center">
				Hi! I’m Jaedon Smith, a Computer Science student at Toronto Metropolitan University (TMU),
				expecting to graduate soon. I’m passionate about technology and always eager to dive into
				new tools, languages, and frameworks. I thrive on solving complex problems and enjoy the
				challenge of tackling new concepts, whether through coursework or hands-on projects. My
				adaptability and curiosity drive me to continuously expand my skill set and tackle any task
				with enthusiasm.
			</p>
			<a class="btn btn-primary" href="#contacts">Contact Me</a>
		</div>
	</div>
</section>
<section class="mt-10 flex flex-col items-center justify-center">
	<h2 class="mx-auto text-5xl font-bold">Projects</h2>
	<div id="projects" class="py-15 flex w-auto flex-wrap justify-center space-x-3 space-y-3">
		{#each projects as project}
			<div class="card bg-base-300 w-96 shadow-md">
				<figure>
					<img src={project.imageURL} alt={project.name} />
				</figure>
				<div class="card-body">
					<h2 class="card-title">{project.name}</h2>
					<p>
						{project.description}
					</p>
					<div class="card-actions justify-center">
						{#each project.badges as badge}
							<div class="badge badge-neutral">
								{badge}
							</div>
						{/each}
					</div>
					<a class="btn btn-primary border-0 shadow-none" href={project.link}>Check It Out</a>
				</div>
			</div>
		{/each}
	</div>
</section>

<section class="mt-10 flex flex-col items-center justify-center">
	<h2 class="text-5xl font-bold">Skills</h2>
	<div id="skills" class="py-15 flex w-auto flex-wrap justify-center space-x-3 space-y-3">
		<div class="flex items-center justify-center">
			<div class="gap-y2 grid grid-cols-1 place-items-center gap-2 xl:grid-cols-3">
				<div class="card card-lg bg-base-300 w-96 shadow-md">
					<div class="card-body">
						<h2 class="card-title mx-auto">Programming Languages</h2>
						<ul class="list bg-base-100 rounded-box shadow-md">
							{#each languages as language}
								<li class="list-row">
									<div>
										<img class="rounded-box size-10 object-cover" src={language.imageURL} />
									</div>
									<div class="flex flex-col items-start justify-center">
										<div class="text-xs font-semibold uppercase opacity-60">{language.name}</div>
									</div>
								</li>
							{/each}
						</ul>
						<div class="card-actions justify-end"></div>
					</div>
				</div>
				<div class="card card-lg bg-base-300 w-96 shadow-md">
					<div class="card-body">
						<h2 class="card-title mx-auto">Libraries & Frameworks</h2>
						<ul class="list bg-base-100 rounded-box shadow-md">
							{#each libraries as library}
								<li class="list-row">
									<div>
										<img class="rounded-box size-10 object-fill" src={library.imageURL} />
									</div>
									<div class="flex flex-col items-start justify-center">
										<div class="text-xs font-semibold uppercase opacity-60">{library.name}</div>
									</div>
								</li>
							{/each}
						</ul>
						<div class="card-actions justify-end"></div>
					</div>
				</div>
				<div class="card card-lg bg-base-300 w-96 shadow-md">
					<div class="card-body">
						<h2 class="card-title mx-auto">Tools</h2>
						<ul class="list bg-base-100 rounded-box shadow-md">
							{#each tools as tool}
								<li class="list-row">
									<div>
										<img class="rounded-box size-10 object-fill" src={tool.imageURL} />
									</div>
									<div class="flex flex-col items-start justify-center">
										<div class="text-xs font-semibold uppercase opacity-60">{tool.name}</div>
									</div>
								</li>
							{/each}
						</ul>
						<div class="card-actions justify-end"></div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<section id="contacts" class="mt-10 flex flex-col items-center justify-center">
	<h2 class="text-5xl font-bold">Contact</h2>
	<div class="py-15 flex w-auto flex-wrap justify-center space-x-3 space-y-3">
		<div class="bg-base-300 w-100 container mx-auto max-w-sm space-y-4 rounded-lg p-6 shadow-md">
			<fieldset class="fieldset">
				<legend class="fieldset-legend">Email</legend>
				<input
					name="email"
					class="input validator"
					type="email"
					required
					placeholder="Enter Email"
					oninput={(e) => handleEmail(e)}
				/>
				<div class="validator-hint">Enter valid email address</div>
			</fieldset>
			<fieldset class="fieldset">
				<legend class="fieldset-legend">Subject</legend>
				<input
					name="subject"
					type="text"
					class="input"
					placeholder="Enter Subject"
					oninput={(e) => handleSubject(e)}
				/>
			</fieldset>
			<fieldset class="fieldset">
				<legend class="fieldset-legend">Message</legend>
				<textarea
					name="message"
					class="textarea"
					placeholder="Type Message"
					oninput={(e) => handleMessage(e)}
				></textarea>
			</fieldset>
			<a
				href={`mailto:${email}?subject=${subject}&body=${message}`}
				class="btn btn-wide btn-primary mx-auto">Contact Me</a
			>
		</div>
	</div>
</section>
<footer class="footer footer-center bg-base-300 text-base-content mt-10 p-10">
	<div>
		<p>Copyright © 2025 - All right reserved by Jaedon Smith</p>
	</div>
</footer>
