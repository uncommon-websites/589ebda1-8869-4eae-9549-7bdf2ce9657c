<script lang="ts">
	import { onMount } from 'svelte';

	let email = '';
	
	const faqs = [
		{ question: "How is Nummo different from Excel or Google Sheets?", answer: "Nummo stores models as semantic graphs rather than cell grids. Each metric is a defined concept with tracked dependencies, enabling AI to build, audit, and extend models deterministically. This means you get the power of Excel with AI that actually understands your model structure, not just cell references." },
		{ question: "Do I need to learn new keyboard shortcuts?", answer: "No. Nummo maintains Excel keyboard shortcut parity across both Mac and PC, eliminating the tragic offboarding when switching between devices. All your Alt and Ctrl shortcuts work exactly as expected, so you can work with zero learning curve while gaining powerful new capabilities." },
		{ question: "Can Nummo work offline?", answer: "Yes. Nummo is local-first and computes on your machine by default. You can build and edit models without internet connectivity, which is critical for working on planes, in secure environments, or anywhere without reliable internet. Your data stays on your machine." },
		{ question: "How does Nummo handle sensitive financial data?", answer: "Raw numbers never leave your desktop by default. Data can only flow in, never out. We offer custom LLM deployment and on-premises options for PE funds, investment banks, and regulated institutions. Your security team can audit exactly how data flows through the system." },
		{ question: "What happens to my model history?", answer: "Every .nummo file contains your complete model history - every version, query, source, and manual change. You can branch, compare, and commit changes with git-style version control. This means you can hand off a single file that contains everything your colleague needs to understand the model's evolution." },
		{ question: "Can I integrate with my existing data sources?", answer: "Yes. Nummo's Research Center pulls live data from FactSet, SEC filings, earnings calls, and your internal systems. We support custom integrations with financial research providers, accounting software, data room providers, and proprietary data feeds. Your data flows directly into your models without manual copy-paste." },
		{ question: "Is Nummo suitable for complex LBO and DCF models?", answer: "Absolutely. Nummo is built specifically for investment banking and private equity workflows including LBO models, DCF analysis, merger models, portfolio company operating models, and scenario planning. The semantic graph architecture handles circular references, complex dependencies, and multi-case modeling that would break traditional spreadsheets." },
		{ question: "How does the AI understand my models?", answer: "The semantic graph structure is retained by LLMs, enabling deterministic changes. Instead of treating your model as a grid of cells, AI understands concepts like 'Revenue Growth Rate' and 'EBITDA Margin' with their dependencies. This means AI can make intelligent changes that propagate correctly through your entire model, not just modify individual cells." },
		{ question: "Can I share models with my team?", answer: "Yes. The single .nummo file format simplifies sharing - no more emailing multiple versions or losing track of changes. Source Visualization shows the origin of every number, making handoffs seamless. Your colleague can see exactly where each assumption came from and what data sources were used." },
		{ question: "What if I don't like a change the AI made?", answer: "Nummo includes full version control with branching and checkpoints. You can compare any two versions side-by-side, revert to any previous state with one click, or create branches to test scenarios without affecting your main model. Every change is tracked and reversible." },
		{ question: "Who is Nummo built for?", answer: "Nummo is purpose-built for power users in finance: VC and PE associates doing diligence models and portfolio tracking, investment banking analysts building LBO and DCF models, strategic finance teams doing scenario planning, and anyone who lives in spreadsheets and needs their models to work for them, not against them." },
		{ question: "How does the .nummo file format work?", answer: "The .nummo file format encapsulates everything: your model structure, all queries, manual changes, research context, data sources, and hundreds of versions in one seamless file. This eliminates the nightmare of tracking multiple Excel versions, external data files, and email chains. One file contains the complete story of your model." }
	];
</script>

<div class="min-h-screen bg-dark-bg text-white font-sans selection:bg-brand-green selection:text-dark-bg">
	
	<!-- Announcement Banner -->
	<div class="w-full bg-dark-bg py-3 text-center text-[10px] tracking-widest uppercase border-b border-white/5">
		<span class="text-gray-400">Capturing the</span> <span class="text-brand-green">$8B Financial Modeling Market</span>
	</div>

	<!-- Navigation -->
	<nav class="flex items-center justify-between px-6 py-5 max-w-7xl mx-auto">
		<div class="flex items-center gap-8">
			<a href="/" class="text-2xl font-serif tracking-tight font-medium">Nummo</a>
			<div class="hidden md:flex gap-6 text-sm text-gray-400">
				<a href="#security" class="hover:text-white transition-colors">Security</a>
				<a href="#features" class="hover:text-white transition-colors">Features</a>
			</div>
		</div>
		<a href="#contact" class="text-sm text-white hover:text-gray-300 transition-colors">Contact Sales</a>
	</nav>

	<!-- Hero Section -->
	<section class="pt-24 pb-40 px-4 text-center max-w-6xl mx-auto relative z-10">
		<h1 class="text-6xl md:text-8xl font-serif mb-8 tracking-tight leading-[0.95]">The spreadsheet<br/>purpose-built for<br/>power users</h1>
		<p class="text-gray-400 text-xl md:text-2xl mb-12 max-w-3xl mx-auto font-light leading-relaxed">
			Work offline. Pull in data from anywhere. Track every source at a glance. AI sits inside your models, building and reviewing without you ever leaving your spreadsheet.
		</p>

		<div class="flex flex-col sm:flex-row items-center justify-center gap-3 mb-6 max-w-md mx-auto">
			<input 
				type="email" 
				placeholder="Work email" 
				bind:value={email}
				class="w-full sm:w-64 bg-[#0A1F1E] border border-white/10 rounded-lg px-5 py-3 text-sm text-white placeholder-gray-500 focus:outline-none focus:border-brand-green/50 transition-colors"
			/>
			<button class="w-full sm:w-auto bg-white text-dark-bg px-8 py-3 rounded-lg text-sm font-semibold hover:bg-gray-100 transition-all hover:scale-[1.02]">
				Get Early Access
			</button>
		</div>
		
		<p class="text-xs text-gray-500">Enterprise deployment available for PE funds, VCs, and investment banks</p>
	</section>

	<!-- Hero Product Screenshot -->
	<div class="relative max-w-7xl mx-auto px-4 -mt-20 mb-40">
		<div class="rounded-2xl overflow-hidden border border-white/10 shadow-2xl bg-[#1a1a1a] relative group">
			<!-- Actual Product Screenshot -->
			<img 
				src="/uploaded/1765870008903-rprkson.png" 
				alt="Nummo financial modeling interface showing Ingevity Model with operating assumptions, chat agent, and version control"
				class="w-full h-auto"
			/>
			
			<!-- Subtle overlay gradient for depth -->
			<div class="absolute inset-0 bg-gradient-to-t from-dark-bg/20 to-transparent pointer-events-none"></div>
			
			<!-- Floating feature callouts -->
			<div class="absolute top-8 left-8 bg-black/80 backdrop-blur-md border border-white/20 rounded-xl px-4 py-3 text-xs max-w-xs opacity-0 group-hover:opacity-100 transition-opacity duration-500">
				<div class="text-brand-green font-semibold mb-1">AI Chat Agent</div>
				<div class="text-gray-300 text-[11px] leading-relaxed">Ask questions, build models, and review assumptions without leaving your spreadsheet</div>
			</div>
			
			<div class="absolute bottom-8 right-8 bg-black/80 backdrop-blur-md border border-white/20 rounded-xl px-4 py-3 text-xs max-w-xs opacity-0 group-hover:opacity-100 transition-opacity duration-500 delay-100">
				<div class="text-brand-green font-semibold mb-1">Version Control Built In</div>
				<div class="text-gray-300 text-[11px] leading-relaxed">Track every change with git-style versioning and checkpoint management</div>
			</div>
		</div>
		
		<!-- Refined gradient glows -->
		<div class="absolute -top-32 -left-32 w-[500px] h-[500px] bg-brand-green/5 rounded-full blur-[120px] -z-10"></div>
		<div class="absolute -bottom-32 -right-32 w-[500px] h-[500px] bg-brand-green/3 rounded-full blur-[120px] -z-10"></div>
	</div>

	<!-- Auditable Section -->
	<section class="bg-white text-dark-bg py-32">
		<div class="max-w-7xl mx-auto px-6 grid md:grid-cols-2 gap-20 items-center">
			<div>
				<h2 class="text-5xl md:text-6xl font-serif mb-8 leading-tight">Every number,<br/>fully traced</h2>
				<p class="text-gray-600 text-xl leading-relaxed mb-8">
					Source Visualization shows the origin of every number in your model. AI builds formulas, audits dependencies, and catches errors before they reach your MD.
				</p>
				<p class="text-gray-500 text-base leading-relaxed">
					Models are stored as semantic graphs where each metric is a defined concept with tracked dependencies. This structure enables AI to make deterministic, explainable changes while you maintain complete visibility into every assumption and driver.
				</p>
			</div>
			<div class="relative">
				<!-- Product screenshot showing dependency tracking -->
				<div class="bg-white rounded-2xl shadow-2xl border border-gray-200 overflow-hidden transform hover:rotate-0 rotate-1 transition-transform duration-500">
					<div class="bg-gray-50 border-b border-gray-200 px-6 py-3 text-sm text-gray-700 font-semibold flex items-center justify-between">
						<span>Operating Model - Assumptions</span>
						<span class="text-xs text-gray-500 font-normal">47 dependencies tracked</span>
					</div>
					<div class="p-6 space-y-4 font-mono text-sm">
						<div class="flex justify-between border-b border-gray-100 pb-3">
							<span class="text-gray-600">Tax Rate</span> 
							<span class="font-semibold">35.0%</span>
						</div>
						<div class="flex justify-between border-b border-gray-100 pb-3">
							<span class="text-gray-600">Yield on Cash</span> 
							<span class="font-semibold">1.0%</span>
						</div>
						<div class="flex justify-between border-b border-gray-100 pb-3">
							<span class="text-gray-600">Maintenance Capex % of Revenue</span> 
							<span class="font-semibold">5.0%</span>
						</div>
						<div class="flex justify-between font-bold bg-green-50 p-3 rounded-lg relative group cursor-help border border-green-200">
							<span>Exit EV/EBITDA Multiple</span> 
							<span class="text-brand-green-dim">12.0x</span>
							<!-- Tooltip showing dependencies -->
							<div class="absolute bottom-full left-1/2 -translate-x-1/2 mb-3 w-64 bg-white shadow-xl rounded-lg p-4 border border-gray-200 text-xs font-sans text-gray-600 hidden group-hover:block z-10">
								<div class="font-semibold text-black mb-3 text-sm">Dependencies Tracked:</div>
								<div class="space-y-2 text-gray-500">
									<div class="flex items-start gap-2">
										<span class="text-brand-green mt-0.5">→</span>
										<span>Revenue!B12 (Growth assumptions)</span>
									</div>
									<div class="flex items-start gap-2">
										<span class="text-brand-green mt-0.5">→</span>
										<span>EBITDA!C4:C8 (Margin structure)</span>
									</div>
									<div class="flex items-start gap-2">
										<span class="text-brand-green mt-0.5">→</span>
										<span>Comps!D2 (Market multiples)</span>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Grid Section -->
	<section class="bg-white text-dark-bg pb-32">
		<div class="max-w-7xl mx-auto px-6 grid md:grid-cols-2 gap-10">
			<!-- Card 1 -->
			<div class="bg-gray-50 rounded-3xl p-10 md:p-14 hover:bg-gray-100 transition-colors duration-300">
				<h3 class="text-3xl font-serif mb-5 leading-tight">Semantic graph architecture</h3>
				<p class="text-gray-600 mb-10 text-base leading-relaxed">
					Models stored as structured, semantic graphs rather than cell grids. Each metric is a defined concept tied to assumptions, drivers, and dependencies. This graph structure is retained by LLMs, enabling deterministic and explainable changes that you can audit end-to-end.
				</p>
				<div class="bg-white rounded-2xl shadow-sm border border-gray-200 p-10 h-56 flex items-center justify-center relative overflow-hidden">
					<!-- Network nodes -->
					<div class="relative w-full h-full">
						<div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-16 h-16 rounded-full bg-brand-green/20 border-2 border-brand-green flex items-center justify-center">
							<div class="text-[10px] font-bold text-brand-green-dim">EBITDA</div>
						</div>
						<div class="absolute top-6 left-10 w-10 h-10 rounded-full bg-gray-100 border border-gray-300 flex items-center justify-center">
							<div class="text-[8px] text-gray-500 font-medium">Rev</div>
						</div>
						<div class="absolute top-6 right-10 w-10 h-10 rounded-full bg-gray-100 border border-gray-300 flex items-center justify-center">
							<div class="text-[8px] text-gray-500 font-medium">COGS</div>
						</div>
						<div class="absolute bottom-6 left-14 w-10 h-10 rounded-full bg-gray-100 border border-gray-300 flex items-center justify-center">
							<div class="text-[8px] text-gray-500 font-medium">OpEx</div>
						</div>
						<div class="absolute bottom-6 right-14 w-10 h-10 rounded-full bg-gray-100 border border-gray-300 flex items-center justify-center">
							<div class="text-[8px] text-gray-500 font-medium">D&A</div>
						</div>
						<!-- Connection lines -->
						<svg class="absolute inset-0 w-full h-full pointer-events-none" style="z-index: 0;">
							<line x1="50%" y1="50%" x2="20%" y2="20%" stroke="#d1d5db" stroke-width="1.5"/>
							<line x1="50%" y1="50%" x2="80%" y2="20%" stroke="#d1d5db" stroke-width="1.5"/>
							<line x1="50%" y1="50%" x2="30%" y2="80%" stroke="#d1d5db" stroke-width="1.5"/>
							<line x1="50%" y1="50%" x2="70%" y2="80%" stroke="#d1d5db" stroke-width="1.5"/>
						</svg>
					</div>
					<!-- Floating labels -->
					<div class="absolute top-5 left-5 bg-white shadow-md rounded-lg px-3 py-1.5 text-[10px] border border-gray-100 text-gray-500 font-medium">47 dependencies</div>
				</div>
			</div>
			<!-- Card 2 -->
			<div class="bg-gray-50 rounded-3xl p-10 md:p-14 hover:bg-gray-100 transition-colors duration-300">
				<h3 class="text-3xl font-serif mb-5 leading-tight">Local-first architecture</h3>
				<p class="text-gray-600 mb-10 text-base leading-relaxed">
					Models compute locally on your machine by default. Offline-first design ensures work continues without internet connectivity. Every .nummo file contains your complete model history: every version, query, source, and manual change in one seamless handoff.
				</p>
				<div class="bg-white rounded-2xl shadow-sm border border-gray-200 p-8 h-56 flex items-center justify-center relative">
					<!-- Desktop icon -->
					<div class="relative">
						<div class="w-40 h-24 bg-gray-100 rounded-t-lg border-2 border-gray-300"></div>
						<div class="w-48 h-3 bg-gray-300 rounded-b-lg -mt-px"></div>
						<div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 text-center">
							<div class="text-3xl mb-2">💻</div>
							<div class="text-[10px] text-gray-600 font-semibold">Local Compute</div>
						</div>
					</div>
					<!-- Floating badge -->
					<div class="absolute top-5 right-5 bg-brand-green/10 border border-brand-green/30 rounded-full px-4 py-1.5 text-[10px] font-semibold text-brand-green-dim">
						Offline Ready
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Testimonial -->
	<section class="bg-dark-bg text-white py-40 relative overflow-hidden">
		<div class="max-w-4xl mx-auto px-6 text-center relative z-10">
			<div class="text-brand-green text-6xl font-serif absolute -top-10 left-0 opacity-50">“</div>
			<blockquote class="text-3xl md:text-4xl font-serif leading-tight mb-12 relative">
				<span class="text-brand-green absolute -left-4 -top-4">“</span>
				Nummo eliminated our nightly fire drills. The AI caught three errors in our LBO model before we sent it to the MD. This is the future of financial modeling.
				<span class="text-brand-green absolute -right-4 bottom-4">”</span>
			</blockquote>
			<div class="flex items-center justify-between border-t border-white/10 pt-8">
				<div class="text-sm font-mono tracking-wide uppercase text-gray-400">Associate at PE Fund</div>
				<div class="flex gap-2">
					<button class="w-8 h-8 border border-white/20 flex items-center justify-center hover:bg-white/10 transition-colors">
						<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M15 18l-6-6 6-6"/></svg>
					</button>
					<button class="w-8 h-8 border border-white/20 flex items-center justify-center hover:bg-white/10 transition-colors">
						<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 18l6-6-6-6"/></svg>
					</button>
				</div>
			</div>
		</div>
	</section>

	<!-- Features Grid -->
	<section class="bg-white text-dark-bg py-24">
		<div class="text-center mb-20" id="features">
			<div class="text-[10px] uppercase tracking-widest text-gray-500 mb-6">+FEATURES</div>
			<h2 class="text-5xl md:text-7xl font-serif mb-6 leading-tight">
				Built for investment<br/>banking workflows
			</h2>
			<p class="text-gray-600 text-xl mb-8 max-w-3xl mx-auto">From LBO models to DCF analysis, merger models to portfolio company operating models, Nummo handles the complex financial modeling that drives deals</p>
			<div class="flex items-center justify-center gap-2 text-gray-500 text-sm font-semibold">
				<svg class="w-4 h-4" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2L2 7v10c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V7l-10-5z"/></svg>
				Desktop application for Mac & PC
			</div>
		</div>

		<!-- Feature Nav -->
		<div class="flex flex-wrap justify-center gap-6 text-sm text-gray-400 mb-16 border-b border-gray-100 pb-4 max-w-6xl mx-auto px-6">
			<span>Semantic Graphs</span>
			<span>Version Control</span>
			<span>Research Center</span>
			<span class="text-black font-medium border-b-2 border-black pb-4 -mb-4.5">AI Chat Agent</span>
			<span>Source Visualization</span>
			<span>Model Templates</span>
			<span>Scenario Planning</span>
			<span>Data Integration</span>
		</div>

		<div class="max-w-6xl mx-auto px-6 space-y-8">
			<!-- Row 1: Dependency Tracking -->
			<div class="bg-gray-50 rounded-2xl p-8 md:p-12 grid md:grid-cols-2 gap-12 items-center">
				<div>
					<h3 class="text-2xl font-serif mb-4">Complete Dependency Tracking</h3>
					<p class="text-gray-600 text-sm leading-relaxed">
						Every metric is a semantic concept with tracked dependencies. Navigate complex models end-to-end with full visibility into assumptions and drivers.
					</p>
				</div>
				<div class="bg-white shadow-lg shadow-gray-200/50 border border-gray-200 rounded-lg p-6 transform rotate-1 transition-transform hover:rotate-0">
					<div class="flex items-center gap-4 mb-4 text-[10px] text-gray-400 border-b border-gray-100 pb-2">
						<div class="w-4 text-center">I</div>
						<div class="w-16 text-center">J</div>
						<div class="w-16 text-center">K</div>
						<div class="w-16 text-center">L</div>
					</div>
					<!-- Fake table -->
					<div class="grid grid-cols-4 gap-y-3 text-xs font-mono">
						<div class="text-gray-400 text-[10px] self-center">21</div> <div class="col-span-1 text-gray-500">PF Revenue</div> <div class="col-span-2 text-right">$110,000</div>
						<div class="text-gray-400 text-[10px] self-center">22</div> <div class="col-span-1 text-gray-500">PF COGS</div> <div class="col-span-2 text-right">$31,252</div>
						<div class="col-span-4 h-px bg-gray-100 my-1"></div>
						<div class="text-gray-400 text-[10px] self-center">23</div> <div class="col-span-1 font-bold text-black">Base Gross Profit</div> <div class="col-span-2 text-right font-bold text-black bg-green-50 px-1 rounded border border-green-100 relative">
							$72,000
							<div class="absolute top-0 right-0 w-1.5 h-1.5 bg-green-500 rounded-full -mt-0.5 -mr-0.5"></div>
						</div>
						<div class="text-gray-400 text-[10px] self-center">24</div> <div class="col-span-1 text-gray-500">FX Gains (add-back)</div> <div class="col-span-2 text-right">$1,200</div>
						<div class="text-gray-400 text-[10px] self-center">25</div> <div class="col-span-1 text-gray-500">Inventory Fair Value</div> <div class="col-span-2 text-right">$2,100</div>
					</div>
				</div>
			</div>

			<!-- Row 2: Navigate & Firm Templates -->
			<div class="grid md:grid-cols-2 gap-8">
				<div class="bg-[#E6F4F1] rounded-2xl p-8 md:p-12 relative overflow-hidden">
					<div class="relative z-10">
						<div class="flex items-center gap-2 mb-4">
							<div class="w-6 h-6 bg-black rounded flex items-center justify-center text-white text-xs">N</div>
							<span class="text-xs font-semibold uppercase tracking-wider">Nummo • Just now</span>
						</div>
						<p class="text-sm text-gray-800 mb-8 max-w-xs">
							Extended forecast by two years. Updated <span class="bg-green-200 px-1 rounded text-green-800 font-mono text-xs">Revenue!B12</span> growth assumptions and recalculated <span class="bg-green-200 px-1 rounded text-green-800 font-mono text-xs">47 dependent metrics</span> automatically.
						</p>
						<h3 class="text-2xl font-serif mb-2">AI Chat Agent</h3>
						<p class="text-gray-600 text-xs">Chat sits inside your models with full context of dependencies and assumptions</p>
					</div>
				</div>
				<div class="bg-gray-50 rounded-2xl p-8 md:p-12">
					<div class="bg-white rounded-lg shadow-sm border border-gray-200 p-4 mb-8 max-w-xs mx-auto">
						<div class="text-xs font-semibold mb-3 border-b border-gray-100 pb-2">Model Templates</div>
						<div class="space-y-2">
							<div class="flex items-center gap-2 text-xs text-gray-500">
								<div class="w-3 h-3 border border-gray-300"></div> LBO Model
							</div>
							<div class="flex items-center justify-between gap-2 text-xs bg-gray-50 p-2 rounded border border-gray-200">
								<div class="flex items-center gap-2 font-medium">
									<div class="w-3 h-3 border border-gray-400 bg-gray-200"></div> DCF Analysis
								</div>
								<span class="bg-black text-white px-1.5 py-0.5 rounded text-[10px]">Open</span>
							</div>
						</div>
					</div>
					<h3 class="text-2xl font-serif mb-2">PortCo Templates</h3>
					<p class="text-gray-600 text-xs">Portfolio company operating model templates with dynamic revenue builds</p>
				</div>
			</div>

			<!-- Row 3: Keyboard Shortcuts -->
			<div class="bg-gray-50 rounded-2xl p-8 md:p-12 grid md:grid-cols-2 gap-12 items-center">
				<div>
					<h3 class="text-2xl font-serif mb-4">Excel Keyboard Parity</h3>
					<p class="text-gray-600 text-sm leading-relaxed mb-6">
						Maintains Excel keyboard shortcut compatibility for zero learning curve. All your Alt and Ctrl shortcuts work exactly as expected.
					</p>
					<div class="space-y-2 text-xs font-mono text-gray-500">
						<div class="flex justify-between border-b border-gray-200 pb-1"><span>Extend Forecast</span> <span>Ctrl+E</span></div>
						<div class="flex justify-between border-b border-gray-200 pb-1"><span>Branch Model</span> <span>Ctrl+B</span></div>
					</div>
				</div>
				<div class="relative h-48">
					<!-- Keyboard Graphic Placeholder -->
					<div class="absolute inset-0 flex items-center justify-center opacity-20">
						<div class="grid grid-cols-10 gap-1 w-full">
							{#each Array(30) as _}
								<div class="h-8 border border-black rounded"></div>
							{/each}
						</div>
					</div>
				</div>
			</div>

			<!-- Row 4: 3 Cards -->
			<div class="grid md:grid-cols-3 gap-8">
				<div class="bg-gray-50 rounded-2xl p-8">
					<div class="bg-white border border-gray-200 rounded p-4 mb-6 shadow-sm">
						<div class="flex items-center gap-2 mb-2">
							<div class="w-4 h-4 rounded-full bg-black"></div>
							<span class="text-xs font-semibold">Data synced</span>
						</div>
						<div class="flex justify-between items-center text-[10px] text-gray-500">
							<span>FactSet • SEC • Internal</span>
							<span class="underline">View sources</span>
						</div>
					</div>
					<h3 class="text-xl font-serif mb-2">Research Center</h3>
					<p class="text-gray-500 text-xs">Pull live data from public and private sources into your models</p>
				</div>
				<div class="bg-gray-50 rounded-2xl p-8">
					<div class="bg-white border border-gray-200 rounded p-3 mb-6 shadow-sm max-w-[200px]">
						<div class="text-[10px] text-gray-400 mb-1">Version: v2.4.1</div>
						<div class="flex items-center gap-2 text-xs font-medium mb-1">
							<div class="w-4 h-4 bg-black text-white flex items-center justify-center rounded text-[8px]">⟳</div>
							Complete History
						</div>
					</div>
					<h3 class="text-xl font-serif mb-2">Version Control</h3>
					<p class="text-gray-500 text-xs">Branch, compare, and commit changes. Every .nummo file contains full history</p>
				</div>
				<div class="bg-gray-50 rounded-2xl p-8">
					<div class="flex gap-2 mb-6 justify-center">
						<div class="w-8 h-8 rounded-full bg-gray-200"></div>
						<div class="w-8 h-8 rounded bg-black flex items-center justify-center"><div class="w-4 h-4 bg-white/20 grid grid-cols-2 gap-0.5"><div class="bg-white"></div><div class="bg-white"></div><div class="bg-white"></div><div class="bg-white"></div></div></div>
						<div class="w-8 h-8 rounded-full bg-gray-200"></div>
					</div>
					<h3 class="text-xl font-serif mb-2">Custom LLM Options</h3>
					<p class="text-gray-500 text-xs">Custom LLM deployment and on-premises options for regulated institutions</p>
				</div>
			</div>

			<!-- Row 5: 2 Cards -->
			<div class="grid md:grid-cols-2 gap-8">
				<div class="bg-gray-50 rounded-2xl p-8 flex flex-col justify-between">
					<div class="bg-white border border-gray-200 rounded-full px-4 py-2 shadow-sm self-start mb-8 flex items-center gap-4 text-xs">
						<span class="text-gray-400">Reverted to v2.3.8</span>
						<span class="font-bold">Branch</span>
					</div>
					<div>
						<h3 class="text-xl font-serif mb-2">Branch & Revert</h3>
						<p class="text-gray-500 text-xs">Create branches for scenarios, revert to any previous state instantly</p>
					</div>
				</div>
				<div class="bg-gray-50 rounded-2xl p-8">
					<div class="bg-black text-white rounded px-3 py-1.5 text-xs inline-flex items-center gap-2 mb-4">
						<svg class="w-3 h-3" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" /></svg>
						Conversion completed
					</div>
					<div class="flex gap-4 mb-8">
						<div class="w-1/3 bg-white border border-gray-200 h-20 rounded p-2">
							<div class="h-2 w-12 bg-gray-200 mb-2"></div>
							<div class="h-1 w-full bg-gray-100 mb-1"></div>
							<div class="h-1 w-full bg-gray-100 mb-1"></div>
						</div>
						<div class="w-2/3 bg-white border border-gray-200 h-20 rounded p-2 grid grid-cols-3 gap-1">
							<div class="bg-gray-50 h-full"></div>
							<div class="bg-gray-50 h-full"></div>
							<div class="bg-gray-50 h-full"></div>
						</div>
					</div>
					<h3 class="text-xl font-serif mb-2">Scenario Planning</h3>
					<p class="text-gray-500 text-xs">Automated control panels for base, bull, and bear cases with multi-case modeling</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Data Sources -->
	<section class="bg-dark-bg text-white py-24 border-t border-white/5">
		<div class="max-w-4xl mx-auto px-6 text-center">
			<div class="text-[10px] uppercase tracking-widest text-gray-500 mb-6">+DATA SOURCES</div>
			<h2 class="text-4xl md:text-6xl font-serif mb-8 leading-tight">Research Center integrates<br/>with your data sources</h2>
			<p class="text-gray-400 text-lg mb-16 max-w-2xl mx-auto leading-relaxed">Pull live data from FactSet, SEC filings, earnings calls, and your internal systems. Sync with data room providers and custom integrations for seamless deal workflows.</p>

			<div class="bg-[#0A1F1E] border border-white/10 rounded-xl overflow-hidden max-w-md mx-auto relative">
				<div class="p-4 flex items-center gap-4 border-b border-white/5 bg-[#0F2928] relative z-10">
					<div class="w-8 h-8 bg-white rounded flex items-center justify-center shadow-lg shadow-brand-green/20">
						<div class="w-4 h-4 bg-black grid grid-cols-2 gap-0.5"><div class="bg-white"></div><div class="bg-white"></div><div class="bg-white"></div><div class="bg-white"></div></div>
					</div>
					<div class="text-left">
						<div class="text-sm font-medium text-white">Nummo Research Center</div>
						<div class="text-[10px] text-brand-green flex items-center gap-1">
							<span class="w-1 h-1 bg-brand-green rounded-full animate-pulse"></span>
							Syncing data sources...
						</div>
					</div>
				</div>
				
				<!-- Connecting line visual -->
				<div class="absolute left-8 top-12 bottom-0 w-px bg-gradient-to-b from-white/20 to-transparent z-0"></div>

				<div class="divide-y divide-white/5 text-sm text-gray-400 text-left relative z-10">
					<div class="p-4 pl-16 hover:bg-white/5 transition-colors cursor-pointer flex items-center justify-between group">
						<span>FactSet</span>
						<span class="opacity-0 group-hover:opacity-100 text-xs text-brand-green">Connected</span>
					</div>
					<div class="p-4 pl-16 hover:bg-white/5 transition-colors cursor-pointer flex items-center justify-between group">
						<span>SEC Filings</span>
						<span class="opacity-0 group-hover:opacity-100 text-xs text-brand-green">Connected</span>
					</div>
					<div class="p-4 pl-16 hover:bg-white/5 transition-colors cursor-pointer flex items-center justify-between group">
						<span>Earnings calls</span>
						<span class="opacity-0 group-hover:opacity-100 text-xs text-brand-green">Connected</span>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Security -->
	<section id="security" class="bg-white text-dark-bg py-24">
		<div class="max-w-6xl mx-auto px-6 grid md:grid-cols-2 gap-16">
			<div>
				<div class="text-[10px] uppercase tracking-widest text-gray-500 mb-6">+SECURITY</div>
				<h2 class="text-5xl md:text-6xl font-serif mb-8 leading-tight">Your data never<br/>leaves your desktop</h2>
				<p class="text-gray-600 text-lg mb-6 leading-relaxed">
					Local-first architecture means raw numbers stay on your machine by default. Data can only flow in, never out.
				</p>
				<p class="text-gray-600 text-base mb-10 leading-relaxed">
					Custom LLM deployment and on-premises options available for PE funds, investment banks, and compliance-heavy organizations. We work with your security team to meet your specific requirements.
				</p>
				<a href="#" class="inline-flex items-center gap-2 font-medium text-base hover:underline">
					<div class="w-5 h-5 bg-black text-white flex items-center justify-center rounded-sm text-xs">→</div>
					Enterprise deployment options
				</a>
			</div>
			<div class="grid grid-cols-2 gap-px bg-gray-200 border border-gray-200">
				<!-- SOC 2 -->
				<div class="bg-white p-8 flex items-center justify-center aspect-square">
					<div class="w-24 h-24 rounded-full border-2 border-black flex flex-col items-center justify-center relative p-2">
						<div class="absolute inset-1 border border-black rounded-full"></div>
						<div class="text-[8px] uppercase tracking-widest font-semibold mb-1">AICPA</div>
						<div class="text-lg font-bold leading-none">SOC</div>
						<div class="text-[10px] font-bold">2</div>
					</div>
				</div>
				<!-- ISO -->
				<div class="bg-white p-8 flex items-center justify-center aspect-square">
					<div class="w-24 h-24 rounded-full border-2 border-black flex flex-col items-center justify-center relative p-2">
						<div class="absolute inset-1 border border-dashed border-black rounded-full"></div>
						<div class="text-xl font-bold">ISO</div>
						<div class="text-[10px] font-bold bg-black text-white px-1 rounded-sm mt-1">27001</div>
					</div>
				</div>
				<!-- CCPA -->
				<div class="bg-white p-8 flex items-center justify-center aspect-square">
					<div class="w-24 h-24 rounded-full border border-black flex flex-col items-center justify-center relative p-2">
						<div class="text-lg font-serif">CCPA</div>
						<div class="text-[8px] uppercase tracking-widest mt-1">Ready</div>
					</div>
				</div>
				<!-- GDPR -->
				<div class="bg-white p-8 flex items-center justify-center aspect-square">
					<div class="w-24 h-24 rounded-full border border-dashed border-black flex flex-col items-center justify-center relative p-2">
						<div class="absolute top-2 text-[10px]">* * *</div>
						<div class="text-lg font-bold">GDPR</div>
						<div class="absolute bottom-2 text-[10px]">* * *</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- FAQs -->
	<section class="bg-white text-dark-bg pb-32">
		<div class="max-w-3xl mx-auto px-6">
			<div class="text-[10px] uppercase tracking-widest text-gray-500 mb-6">+FAQS</div>
			<h2 class="text-5xl md:text-6xl font-serif mb-16 leading-tight">Frequently asked<br/>questions</h2>

			<div class="border-t border-gray-200">
				{#each faqs as faq}
					<details class="group border-b border-gray-200">
						<summary class="flex justify-between items-center py-6 cursor-pointer list-none">
							<span class="font-medium text-lg pr-8">{faq.question}</span>
							<span class="transition group-open:rotate-45">
								<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1"><path d="M12 5v14M5 12h14"/></svg>
							</span>
						</summary>
						<div class="text-gray-600 pb-6 leading-relaxed">
							{faq.answer}
						</div>
					</details>
				{/each}
			</div>
		</div>
	</section>

	<!-- CTA Footer -->
	<section class="bg-dark-bg text-white py-32 relative overflow-hidden">
		<!-- Grid Background Effect -->
		<div class="absolute inset-0 opacity-20 pointer-events-none" 
			 style="background-image: linear-gradient(rgba(255,255,255,0.05) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.05) 1px, transparent 1px); background-size: 50px 50px;">
		</div>
		<div class="absolute bottom-0 left-0 right-0 h-64 bg-gradient-to-t from-brand-green/20 to-transparent pointer-events-none"></div>

		<div class="max-w-4xl mx-auto px-6 relative z-10">
			<div class="text-[10px] uppercase tracking-widest text-brand-green mb-4" id="contact">+GET STARTED</div>
			<h2 class="text-5xl md:text-7xl font-serif mb-12 leading-tight">
				The new foundation of financial modeling
			</h2>
			<div class="flex flex-wrap gap-4">
				<button class="bg-white text-dark-bg px-6 py-3 rounded font-medium hover:bg-gray-100 transition-colors">
					Contact Sales
				</button>
				<button class="bg-white text-dark-bg px-6 py-3 rounded font-medium hover:bg-gray-100 transition-colors">
					Request Demo
				</button>
			</div>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-[#030e0e] text-gray-400 py-12 border-t border-white/5 relative overflow-hidden">
		<div class="max-w-7xl mx-auto px-6 relative z-10">
			<div class="grid grid-cols-2 md:grid-cols-4 gap-8 mb-24 text-sm">
				<div>
					<h4 class="text-white font-semibold mb-4">Product</h4>
				</div>
				<div></div>
				<div></div>
				<div class="text-right">
					<h4 class="text-white font-semibold mb-4">Security</h4>
				</div>
				<div>
					<h4 class="text-white font-semibold mb-4">Legal</h4>
				</div>
				<div class="col-span-3 text-right">
					<div class="space-x-4">
						<a href="#" class="hover:text-white">Privacy</a>
						<span>/</span>
						<a href="#" class="hover:text-white">Terms</a>
						<span>/</span>
						<a href="#" class="hover:text-white">End User License Agreement</a>
					</div>
				</div>
			</div>

			<div class="flex justify-between items-end border-t border-white/5 pt-8">
				<div class="flex items-center gap-4">
					<span class="text-white font-serif text-xl">Nummo</span>
					<span class="text-xs text-gray-600">Nummo 2025. All Rights Reserved</span>
				</div>
				<div class="flex items-center gap-4 text-xs">
					<a href="#" class="hover:text-white">LinkedIn</a>
					<span>/</span>
					<a href="#" class="hover:text-white">X</a>
				</div>
			</div>
		</div>

		<!-- Big Watermark -->
		<div class="absolute bottom-0 left-0 right-0 flex justify-center pointer-events-none overflow-hidden">
			<div class="text-[20vw] font-serif text-white/5 leading-none -mb-10 select-none">
				Nummo
			</div>
		</div>
	</footer>
</div>

<style>
	/* Custom scrollbar for details/summary if needed, but default is fine */
	details > summary {
		list-style: none;
	}
	details > summary::-webkit-details-marker {
		display: none;
	}
</style>

