# Code-practise
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CodePractice - Competitive Programming Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root{
            --dark-bg:#0f0f11;
            --card-bg:#151516;
            --hover-bg:#1f1f20;
            --primary:#1DB954;
            --text-primary:#e8e8e8;
            --text-secondary:#9b9b9b;
        }
        *{box-sizing:border-box;margin:0;padding:0;font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif}
        body{background:linear-gradient(180deg,var(--dark-bg),#0b0b0b);color:var(--text-primary);line-height:1.6}
        .container{max-width:1200px;margin:0 auto;padding:0 20px}
        header{position:sticky;top:0;background:rgba(10,10,10,0.6);backdrop-filter:blur(6px);z-index:50;padding:12px 0}
        nav{display:flex;align-items:center;justify-content:space-between}
        .logo{display:flex;align-items:center;gap:10px;color:var(--primary);font-weight:700;font-size:1.3rem}
        .nav-links{display:flex;gap:18px}
        .nav-links a{color:var(--text-secondary);text-decoration:none}
        .hero{padding:60px 0;background:linear-gradient(180deg,rgba(0,0,0,0.55),rgba(0,0,0,0.55)),url('https://images.unsplash.com/photo-1550439062-609e1531270e?ixlib=rb-4.0.3&auto=format&fit=crop&w=1400&q=80') center/cover no-repeat;border-radius:0 0 10px 10px;margin-bottom:30px}
        .hero h1{font-size:2.4rem;margin-bottom:12px}
        .hero p{color:var(--text-secondary);max-width:760px;margin:0 auto 18px}
        .cta-button{background:var(--primary);color:#000;padding:10px 22px;border-radius:26px;border:none;font-weight:700;cursor:pointer}
        .resources-column {
        margin-left: 400px;
        }
        .section-title{font-size:1.6rem;margin-bottom:18px;color:var(--primary);display:inline-block;padding-bottom:6px;border-bottom:2px solid rgba(29,185,84,0.12)}
        section{padding:40px 0}
        .guide-cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:16px;margin-top:18px}
        .guide-card{background:var(--card-bg);padding:18px;border-radius:10px}
        .guide-card h3{color:var(--primary);margin-bottom:10px}
        .guide-card p{color:var(--text-secondary);font-size:0.95rem}

        .rating-filters{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:18px}
        .rating-filter{background:transparent;border:1px solid rgba(255,255,255,0.04);color:var(--text-secondary);padding:8px 14px;border-radius:20px;cursor:pointer}
        .rating-filter.active{background:var(--primary);color:#000;border-color:transparent}

        .controls{display:flex;gap:12px;align-items:center;margin-bottom:12px}
        .controls input[type="search"]{padding:10px 12px;border-radius:10px;border:1px solid rgba(255,255,255,0.06);background:transparent;color:var(--text-primary)}
        .controls .count{color:var(--text-secondary);font-size:0.95rem}

        .problems-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:14px}
        .problem-card{background:var(--card-bg);padding:16px;border-radius:10px;display:flex;flex-direction:column;gap:10px;transition:transform .15s ease,box-shadow .15s ease}
        .problem-card:hover{transform:translateY(-6px);box-shadow:0 8px 30px rgba(0,0,0,0.6)}
        .problem-meta{display:flex;justify-content:space-between;align-items:center}
        .problem-title{font-size:1.05rem;font-weight:700}
        .problem-tags{display:flex;gap:8px;flex-wrap:wrap}
        .tag{padding:4px 8px;border-radius:999px;font-size:0.8rem;background:rgba(29,185,84,0.08);color:var(--primary)}
        .difficulty{padding:6px 10px;border-radius:999px;font-weight:700}
        .difficulty[data-rating="800"]{background:#2e7d32;color:#fff}
        .difficulty[data-rating="900"]{background:#388e3c;color:#fff}
        .difficulty[data-rating="1000"]{background:#fdd835;color:#000}
        .difficulty[data-rating="1100"]{background:#fb8c00;color:#000}
        .difficulty[data-rating="1200"]{background:#ef5350;color:#fff}
        .difficulty[data-rating="1300"]{background:#8e24aa;color:#fff}
        .prob-actions{display:flex;gap:10px;align-items:center}
        .problem-link{color:var(--primary);text-decoration:none;font-weight:700}

        .loading{color:var(--text-secondary);padding:18px;background:rgba(255,255,255,0.02);border-radius:8px}

        footer{margin-top:40px;padding:30px 0;background:#040404}
        .footer-content{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:18px}
        .footer-column h3{color:var(--primary);margin-bottom:10px}
        .footer-column a, .footer-column p{color:var(--text-secondary);text-decoration:none}

        @media (max-width:768px){
            .hero h1{font-size:1.6rem}
            .nav-links{display:none}
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav>
                <div class="logo"><i class="fas fa-code"></i><span>CodePractice</span></div>
                <div class="nav-links">
                    <a href="#getting-started">Let's Go</a>
                    <a href="#problems">Problems</a>
                    <a href="https://www.geeksforgeeks.org/dsa/competitive-programming-a-complete-guide/" target="_blank">Resources</a>
                    <!-- <a href="#about">About</a> -->
                </div>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container" style="text-align:center">
            <h1>Master Competitive Programming — Live Codeforces Problems</h1>
            <p> "Debug your limits"</p>
            <button class="cta-button" id="start-practice">Start Practicing</button>
        </div>
    </section>

    <section id="getting-started">
        <div class="container">
            <h2 class="section-title">Getting Started with Competitive Programming</h2>
            <div class="guide-cards">
                <div class="guide-card">
                    <h3>Learn the Basics</h3>
                    <p>Start with arrays, strings, pointers, sorting and hashing. Master complexity analysis to pick the right approach.</p>
                </div>
                <div class="guide-card">
                    <h3>Choose a Language</h3>
                    <p>C++ is recommended for contests. Python and Java are fine — know their strengths and limitations.</p>
                </div>
                <div class="guide-card">
                    <h3>Practice Regularly</h3>
                    <p>Solve problems daily. Focused repetition on arrays & strings builds intuition quickly.</p>
                </div>
                <div class="guide-card">
                    <h3>Contests & Analysis</h3>
                    <p>Take part in contests and always analyze editorial/solutions afterwards to learn patterns.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="problems">
        <div class="container">
            <h2 class="section-title">Practice Problems</h2>

            <div class="rating-filters" id="rating-filters" aria-label="Filter by rating">
                <button class="rating-filter active" data-rating="all">All (Live)</button>
                <button class="rating-filter" data-rating="800">800</button>
                <button class="rating-filter" data-rating="900">900</button>
                <button class="rating-filter" data-rating="1000">1000</button>
                <button class="rating-filter" data-rating="1100">1100</button>
                <button class="rating-filter" data-rating="1200">1200</button>
                <button class="rating-filter" data-rating="1300">1300</button>
            </div>

            <div class="controls">
                <input type="search" id="search" placeholder="Search by title or tag (e.g. strings, arrays)" aria-label="Search problems"/>
                <div class="count" id="problems-count">Loading problems…</div>
            </div>

            <div id="loader" class="loading">Fetching problems from Codeforces API — this happens once when the page loads. If this hangs, Codeforces API might be blocked by CORS; you'll get a fallback notice.</div>
            <div class="problems-grid" id="problems-container" aria-live="polite" style="margin-top:12px"></div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>CodePractice</h3>
                    <p>Practice curated problems and build problem-solving patterns for contests                 </p>
                </div>

                <div class="footer-column resources-column">
                <h3>Resources</h3>
                <a href="https://youtu.be/n-Xkbqcfi9w?feature=shared" target="_blank">Video Tutorials</a>
</div>
                </div>
                
            </div>
            <div style="text-align:center;color:var(--text-secondary);margin-top:18px">&copy; Developed by Yug Patel</div>
        </div>
    </footer>

    <script>
        const desiredRatings = [800,900,1000,1100,1200,1300];
        const preferredTagsPerRating = {
            800: ['strings','implementation','arrays','brute force','sorting'],
            900: ['arrays','implementation','sorting','greedy','strings'],
            1000: ['two pointers','strings','hashing','implementation','greedy'],
            1100: ['sorting','binary search','implementation','arrays','strings'],
            1200: ['math','strings','two pointers','greedy','implementation'],
            1300: ['dp','constructive','greedy','graphs','strings']
        };

        const problemsByRating = {};
        const problemsContainer = document.getElementById('problems-container');
        const filters = document.querySelectorAll('.rating-filter');
        const searchInput = document.getElementById('search');
        const countEl = document.getElementById('problems-count');
        const loaderEl = document.getElementById('loader');

        function problemUrl(problem){
            return `https://codeforces.com/problemset/problem/${problem.contestId}/${problem.index}`;
        }

        function scoreProblemForRating(problem, rating){
            const pref = preferredTagsPerRating[rating] || [];
            let score = 0;
            if(problem.tags){
                for(const t of problem.tags){
                    if(pref.includes(t)) score += 10;
                    if(t === 'implementation' || t === 'constructive algorithms') score += 2;
                }
            }
            score += (problem.contestId || 0) / 100000;
            return score;
        }

        function renderProblems(list){
            problemsContainer.innerHTML = '';
            if(!list || !list.length){
                problemsContainer.innerHTML = `<div style="color:var(--text-secondary)">No problems match your query.</div>`;
                countEl.textContent = 'Showing 0 problems';
                return;
            }
            const frag = document.createDocumentFragment();
            list.forEach(p => {
                const card = document.createElement('article');
                card.className = 'problem-card';

                const meta = document.createElement('div');
                meta.className = 'problem-meta';

                const title = document.createElement('div');
                title.innerHTML = `<div class="problem-title">${escapeHtml(p.name)}</div>`;

                const diff = document.createElement('div');
                diff.className = 'difficulty';
                diff.setAttribute('data-rating', p.rating || '—');
                diff.textContent = p.rating || '—';

                meta.appendChild(title);
                meta.appendChild(diff);

                const tagWrap = document.createElement('div');
                tagWrap.className = 'problem-tags';
                (p.tags || []).slice(0,4).forEach(t => {
                    const tEl = document.createElement('span');
                    tEl.className = 'tag';
                    tEl.textContent = t;
                    tagWrap.appendChild(tEl);
                });

                const actions = document.createElement('div');
                actions.className = 'prob-actions';
                const link = document.createElement('a');
                link.className = 'problem-link';
                link.href = problemUrl(p);
                link.target = '_blank';
                link.rel = 'noopener noreferrer';
                link.textContent = 'Open on Codeforces';

                const cp = document.createElement('a');
                cp.href = `https://codeforces.com/contest/${p.contestId}`;
                cp.target = '_blank';
                cp.rel = 'noopener noreferrer';
                cp.className = 'problem-link';
                cp.style.marginLeft = '8px';
                cp.textContent = 'Contest';

                actions.appendChild(link);
                actions.appendChild(cp);

                card.appendChild(meta);
                card.appendChild(tagWrap);
                card.appendChild(actions);
                frag.appendChild(card);
            });
            problemsContainer.appendChild(frag);
            countEl.textContent = `Showing ${list.length} problems`;
        }

        function escapeHtml(unsafe){
            return (unsafe || '')
                .replaceAll('&','&amp;')
                .replaceAll('<','&lt;')
                .replaceAll('>','&gt;')
                .replaceAll('"','&quot;')
                .replaceAll("'","&#039;");
        }

        function applyFilters(){
            let list = [];
            const activeBtn = document.querySelector('.rating-filter.active');
            const activeRating = activeBtn ? activeBtn.dataset.rating : 'all';
            if(activeRating === 'all'){
                list = desiredRatings.flatMap(r => problemsByRating[r] || []).slice(0, desiredRatings.length * 31);
            } else {
                list = (problemsByRating[activeRating] || []).slice();
            }

            const q = searchInput.value.trim().toLowerCase();
            if(q){
                list = list.filter(p => p.name.toLowerCase().includes(q) || (p.tags || []).join(' ').toLowerCase().includes(q));
            }
            renderProblems(list);
        }

        document.getElementById('rating-filters').addEventListener('click', (e) => {
            const btn = e.target.closest('.rating-filter');
            if(!btn) return;
            document.querySelectorAll('.rating-filter').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            applyFilters();
            document.getElementById('problems').scrollIntoView({behavior:'smooth'});
        });

        searchInput.addEventListener('input', () => {
            clearTimeout(window.__searchTimer);
            window.__searchTimer = setTimeout(applyFilters, 200);
        });

        document.getElementById('start-practice').addEventListener('click', ()=>{
            document.querySelector('[data-rating="800"]').click();
        });

        async function fetchProblemsFromCF(){
            try{
                const resp = await fetch('https://codeforces.com/api/problemset.problems');
                if(!resp.ok) throw new Error('Network response not ok');
                const data = await resp.json();
                if(data.status !== 'OK') throw new Error('API returned non-OK');

                const allProblems = data.result.problems || [];
                for(const r of desiredRatings) problemsByRating[r] = [];

                for(const p of allProblems){
                    const r = p.rating;
                    if(desiredRatings.includes(r)){

                        problemsByRating[r].push(p);
                    }
                }

                for(const r of desiredRatings){
                    problemsByRating[r].sort((a,b) => {
                        const sa = scoreProblemForRating(a, r);
                        const sb = scoreProblemForRating(b, r);
                        return sb - sa;
                    });
                    problemsByRating[r] = problemsByRating[r].slice(0,31);
                }

                loaderEl.style.display = 'none';
                document.querySelector('[data-rating="800"]').classList.add('active');
                document.querySelectorAll('.rating-filter').forEach(b => b.classList.remove('active'));
                const btn800 = document.querySelector('[data-rating="800"]');
                if(btn800) btn800.classList.add('active');
                applyFilters();

            } catch(err){
                console.error('Failed to fetch CF API', err);
                loaderEl.innerHTML = 'Failed to load problems from Codeforces API (CORS or network).<br>Your browser will need to allow requests to codeforces.com or use a proxy.\nA fallback placeholder list will be shown instead.';

                const fallback = {
                    800: [
                        {contestId:4,index:'A',name:'Watermelon',rating:800,tags:['math']},
                        {contestId:71,index:'A',name:'Way Too Long Words',rating:800,tags:['strings']},
                        {contestId:231,index:'A',name:'Team',rating:800,tags:['implementation']}
                    ],
                    900: [
                        {contestId:266,index:'B',name:'Queue at the School',rating:900,tags:['implementation','simulation']},
                        {contestId:1328,index:'A',name:'Divisibility Problem',rating:900,tags:['math']}
                    ],
                    1000: [
                        {contestId:1335,index:'A',name:'Candies and Two Sisters',rating:1000,tags:['math']}
                    ],
                    1100: [
                        {contestId:263,index:'A',name:'Beautiful Matrix',rating:1100,tags:['implementation']}
                    ],
                    1200: [
                        {contestId:118,index:'A',name:'String Task',rating:1200,tags:['strings']}
                    ],
                    1300: [
                        {contestId:510,index:'A',name:'Fox And Snake',rating:1300,tags:['implementation']}
                    ]
                };
                for(const r of desiredRatings) problemsByRating[r] = fallback[r] || [];
                applyFilters();
            }
        }
        fetchProblemsFromCF();
        window.addEventListener('keydown', (e) => {
            if(e.key >= '1' && e.key <= '6'){
                const idx = Number(e.key) - 1;
                const r = desiredRatings[idx];
                if(r){
                    const btn = document.querySelector(`[data-rating="${r}"]`);
                    if(btn) btn.click();
                }
            }
        });
        window.__problemsByRating = problemsByRating;
    </script>
</body>
</html>
