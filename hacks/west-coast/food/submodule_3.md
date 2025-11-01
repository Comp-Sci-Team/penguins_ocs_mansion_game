---
layout: opencs
microblog: True
title: "San Francisco"
description: "City Three of Food - San Francisco"
permalink: /west-coast/food/SF/
parent: "San Francisco"
team: "Syntax Terrors"
submodule: 3
categories: [CSP]
tags: [food, sanfrancisco, update, crud]
author: "Syntax Terrors"
date: 2025-10-24
footer:
  previous: /west-coast/food/LA/
  home: /west-coast/food/
  next: /west-coast/food/SEA/
---

<style>
/* === Theme variables (dark-first) === */
:root{
  --bg-0: #060712;            /* page background deep */
  --bg-1: rgba(8,12,25,0.75); /* card background translucent */
  --card-border: rgba(99,102,241,0.18);
  --muted: #94a3b8;
  --text: #e6eef6;
  --accent-1: #8b5cf6;  /* purple */
  --accent-2: #3b82f6;  /* blue */
  --accent-3: #06b6d4;  /* teal/cyan */
  --success: #10b981;
  --danger: #fb7185;
  --glass: rgba(255,255,255,0.03);
  --terminal-bg: #071827;
  --input-border: rgba(148,163,184,0.12);
  --input-bg: rgba(255,255,255,0.02);
  --code-bg: linear-gradient(180deg, rgba(8,12,25,0.6), rgba(12,16,28,0.6));
}

/* Light mode overrides (toggleable) */
body.light {
  --bg-0: #f8fafc;
  --bg-1: rgba(255,255,255,0.96);
  --card-border: rgba(99,102,241,0.14);
  --muted: #6b7280;
  --text: #0b1220;
  --glass: rgba(0,0,0,0.02);
  --terminal-bg: #0b1220;
  --input-bg: #ffffff;
  --input-border: rgba(2,6,23,0.06);
  --code-bg: linear-gradient(180deg, #f8fafc, #eef2ff);
}

/* Base page */
body {
  background: radial-gradient(1200px 500px at 10% 10%, rgba(59,130,246,0.06), transparent),
              radial-gradient(900px 400px at 90% 80%, rgba(139,92,246,0.05), transparent),
              var(--bg-0);
  color: var(--text);
  font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  line-height: 1.5;
  padding: 1.25rem;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* Headings */
h1, h2, h3, h4 { color: #e6e9ff; margin-top: 0.25rem; }
strong { color: #f8f9ff; }

/* Card look (no harsh white) */
.sq-card {
  border-radius: 0.75rem;
  padding: 1rem;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
  border: 1px solid var(--card-border);
  box-shadow: 0 8px 32px rgba(2,6,23,0.45);
  margin-bottom: 1rem;
  backdrop-filter: blur(8px) saturate(1.05);
  transition: transform 0.16s ease, box-shadow 0.2s ease;
}
.sq-card:hover { transform: translateY(-4px); box-shadow: 0 18px 48px rgba(59,130,246,0.08); }

/* Terminal */
.sq-terminal {
  background: var(--terminal-bg);
  color: var(--text);
  padding: 0.75rem;
  border-radius: 0.5rem;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, "Roboto Mono", "Courier New", monospace;
  font-size: 0.9rem;
  min-height: 3rem;
  white-space: pre-wrap;
  overflow: auto;
  border: 1px solid rgba(255,255,255,0.02);
  box-shadow: inset 0 -1px 0 rgba(255,255,255,0.02);
}

/* Buttons */
.sq-btn {
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
  color: var(--text);
  border: 1px solid rgba(255,255,255,0.04);
  padding: 0.55rem 0.9rem;
  border-radius: 0.45rem;
  cursor: pointer;
  font-weight: 600;
  transition: transform 0.12s ease, box-shadow 0.12s ease, background 0.12s ease;
}
.sq-btn:active { transform: translateY(1px) scale(0.998); }

.sq-run {
  background: linear-gradient(90deg, var(--accent-3), rgba(6,182,212,0.15));
  border: 1px solid rgba(6,182,212,0.18);
  color: white;
  box-shadow: 0 8px 20px rgba(6,182,212,0.12);
}

/* Toast */
.sq-toast {
  position: fixed;
  right: 1rem;
  top: 1rem;
  background: linear-gradient(135deg, rgba(139,92,246,0.92), rgba(59,130,246,0.92));
  color: white;
  padding: 0.6rem 1rem;
  border-radius: 0.5rem;
  font-weight: 700;
  display: none;
  z-index: 9999;
  box-shadow: 0 12px 36px rgba(11,12,35,0.5);
}

/* Labels / fields */
.sq-label { display:block; margin-bottom:0.45rem; font-weight:700; color: #e6ebff; }
.sq-field {
  padding:0.6rem;
  border-radius:0.5rem;
  border:1px solid var(--input-border);
  width:100%;
  background: var(--input-bg);
  color: var(--text);
  outline: none;
  box-shadow: inset 0 -1px 0 rgba(255,255,255,0.01);
  font-size: 0.95rem;
}
.sq-field::placeholder { color: var(--muted); }

/* Code editor area */
.code-editor {
  width:100%;
  min-height:120px;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, "Roboto Mono", "Courier New", monospace;
  padding:0.75rem;
  border-radius:0.6rem;
  border:1px dashed rgba(148,163,184,0.08);
  background: var(--code-bg);
  color: var(--text);
  resize: vertical;
  white-space: pre-wrap;
  overflow: auto;
  box-shadow: inset 0 -6px 24px rgba(2,6,23,0.55);
}

/* small helper */
.small { font-size:0.85rem; color: var(--muted); }

/* Progress tracker */
.progress-tracker {
  background: linear-gradient(135deg, rgba(139,92,246,0.06), rgba(59,130,246,0.04));
  border: 1px solid rgba(99,102,241,0.14);
  padding: 1rem;
  border-radius: 0.75rem;
  margin: 1rem 0;
  color: var(--text);
  box-shadow: 0 8px 30px rgba(2,6,23,0.45);
}
.progress-tracker h3 { color: #dbe4ff; margin: 0 0 0.6rem 0; }
.progress-tracker .task-item { margin: 0.35rem 0; color: var(--muted); }

/* Status text */
.task-complete { color: var(--success) !important; font-weight: 700; }

/* Unlock notification (center modal) */
.unlock-notification {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: linear-gradient(135deg, rgba(139,92,246,0.98), rgba(59,130,246,0.98));
  color: white;
  padding: 20px 36px;
  border-radius: 14px;
  font-weight: 700;
  font-size: 16px;
  z-index: 10000;
  box-shadow: 0 30px 80px rgba(11,12,35,0.6);
  display: none;
  text-align: center;
}

/* Back / Next buttons area */
a.back-home {
  background: linear-gradient(135deg, var(--accent-1), var(--accent-2));
  border: 1px solid rgba(139,92,246,0.32);
  padding: 12px 28px;
  border-radius: 22px;
  color: white;
  font-weight: 700;
  text-decoration: none;
  display: inline-block;
  box-shadow: 0 8px 30px rgba(139,92,246,0.12);
}
.next-city-btn {
  position: fixed;
  bottom: 24px;
  right: 24px;
  background: linear-gradient(135deg, var(--accent-3), rgba(6,182,212,0.9));
  color: white;
  padding: 0.75rem 1.25rem;
  border-radius: 0.6rem;
  font-weight: 700;
  font-size: 1rem;
  text-decoration: none;
  box-shadow: 0 14px 40px rgba(6,182,212,0.12);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  z-index: 10000;
}
.next-city-btn:hover { transform: translateY(-3px); }

/* Editor tool row */
.editor-actions { display:flex; gap:0.5rem; align-items:center; flex-wrap:wrap; }

/* small responsive */
@media (max-width: 720px) {
  body { padding: 0.75rem; }
  .sq-card { padding: 0.8rem; }
  .next-city-btn { right: 12px; left: auto; bottom: 12px; font-size: 0.95rem; padding: 0.6rem 1rem; }
}

/* Tiny focus ring for accessibility */
.sq-field:focus, .code-editor:focus, .sq-btn:focus { box-shadow: 0 0 0 4px rgba(59,130,246,0.12); border-color: rgba(59,130,246,0.22); outline: none; }

/* small inline remove button styling */
.ingredients-remove-btn {
  background: transparent;
  color: var(--muted);
  border: none;
  cursor: pointer;
  font-weight: 700;
  margin-left: 8px;
}
.ingredients-remove-btn:hover { color: var(--accent-2); text-decoration: underline; }

/* Custom styles for collapsible details/summary */
summary {
    font-weight: 700;
    font-size: 1.1rem;
    cursor: pointer;
    padding: 0.5rem 0;
    color: #e6e9ff;
    list-style-position: inside;
    list-style-type: '▶ ';
}
details[open] > summary {
    list-style-type: '▼ ';
}
</style>

# 🌉 San Francisco — UPDATE (CRUD Submodule 3)

**Quest Chapter:** *The Food Route*  
**Focus:** U in CRUD — **UPDATE**  
**Location:** San Francisco, CA 🌉🍜

Welcome! This interactive page lets learners *actually* update dishes, ingredients, and join records via simulated API calls — right in the browser.

<!-- Dark mode toggle -->
<div style="display:flex; justify-content:flex-end; gap:0.5rem; margin-bottom:0.75rem;">
  <button id="themeToggleBtn" class="sq-btn" title="Toggle dark / light">🌙 Dark</button>
</div>

<!-- Progress Tracker -->
<div class="progress-tracker">
  <h3>🎯 San Francisco Progress Tracker</h3>
  <div id="progress-display">
    <div id="task-dimsum" class="task-item">Task 1: Dim Sum Menu Updates - <span class="status">Incomplete</span></div>
    <div id="task-chowmein" class="task-item">Task 2: Chowmein Order Updates - <span class="status">Incomplete</span></div>
    <div id="task-sourdough" class="task-item">Task 3: Update Sourdough - <span class="status">Incomplete</span></div>
    <div id="task-seed" class="task-item">Task 4: Seed Pantry - <span class="status">Incomplete</span></div>
    <div id="task-view" class="task-item">Task 5: View Updated Pantry - <span class="status">Incomplete</span></div>
  </div>
  <div style="margin-top: 1rem; padding: 0.75rem; background: rgba(255,255,255,0.01); border-radius: 0.5rem;">
    <strong>Completion: <span id="completion-percentage">0%</span></strong>
    <div style="background: rgba(2,6,23,0.45); height: 8px; border-radius: 6px; margin-top: 0.5rem;">
      <div id="progress-bar" style="background: linear-gradient(90deg, var(--success), #059669); height: 100%; border-radius: 4px; width: 0%; transition: width 0.3s ease;"></div>
    </div>
  </div>
</div>

<div class="sq-toast" id="sqToast">Sourdough updated — +50 XP</div>

<!-- Unlock Notification -->
<div id="unlockNotification" class="unlock-notification">
  🎉 Portland Unlocked!<br>
  <small style="font-size: 13px; opacity: 0.95;">You can now continue to the next city!</small>
</div>

- **🧠 What Does UPDATE Mean?**  
  - In databases, **UPDATE** = modifying existing records (dishes, ingredients, join rows).  
  - On the web, a client form sends a PUT /api/dishes/{id} request.  
  - The server updates:
    - an existing **dish** record,  
    - any missing **ingredient** entries,
    - and **dish_ingredients** join records — ideally inside a transaction (all succeed or all fail).  
  - Analogy: your database is like a **recipe book**. Updating a dish = modifying an existing **recipe card** and adjusting the ingredients while keeping track of all changes.

## How this interactive page works (quick)
- Each task has an editable code area (or an input form) and a **Run** button.
- Running code appends output to the terminal area under the task.
- The page includes a **mock backend** (`MockAPI`) that simulates `PUT /api/dishes/{id}`, `PUT /api/dishes/bulk`, and `GET /api/dishes?city=sf`. Data is stored in `localStorage` so progress persists across refreshes.
- On success when updating Sourdough, a **toast** shows `+50 XP`.

---

# %% Interactive: Mock Backend & Utilities

<div class="sq-card">
  <div style="display:flex; gap:0.5rem; align-items:center;">
    <strong>Initialization:</strong>
    <button class="sq-btn sq-run" onclick="initMock()">Initialize / Reset Mock API</button>
    <span class="small" style="margin-left:0.5rem">Resets mock DB (localStorage) — use this to start fresh.</span>
  </div>

  <div style="margin-top:0.75rem">
    <div class="sq-terminal" id="terminal-init">Terminal: ready</div>
  </div>
</div>

<script>
/* Mock API + utilities for this page. Outputs go to terminal elements using `logTo(id,...)` */
(function () {
  // helpers
  function t() { return Date.now().toString(36).slice(-6); }
    // Task completion tracking
  window.taskProgress = {
    dimsum: false,
    chowmein: false,
    sourdough: false,
    seed: false,
    view: false
  };

  // Load progress from localStorage
  function loadTaskProgress() {
    const saved = localStorage.getItem('sf_task_progress');
    if (saved) {
      try {
        window.taskProgress = { ...window.taskProgress, ...JSON.parse(saved) };
      } catch (e) {
        console.error('Error loading task progress:', e);
      }
    }
    updateProgressDisplay();
  }

  // Save progress to localStorage
  function saveTaskProgress() {
    try {
      localStorage.setItem('sf_task_progress', JSON.stringify(window.taskProgress));
    } catch (e) {
      console.error('Error saving task progress:', e);
    }
  }

  // Mark task as complete
  window.completeTask = function(taskName) {
    if (!window.taskProgress[taskName]) {
      window.taskProgress[taskName] = true;
      saveTaskProgress();
      updateProgressDisplay();
      checkModuleCompletion();
    }
  };

  // Update progress display
  function updateProgressDisplay() {
    const tasks = ['dimsum', 'chowmein', 'sourdough', 'seed', 'view'];
    let completedCount = 0;

    tasks.forEach(task => {
      const element = document.getElementById(`task-${task}`);
      if (element) {
        const statusSpan = element.querySelector('.status');
        if (window.taskProgress[task]) {
          statusSpan.textContent = 'Complete ✅';
          statusSpan.className = 'status task-complete';
          completedCount++;
        } else {
          statusSpan.textContent = 'Incomplete';
          statusSpan.className = 'status';
        }
      }
    });

    // Update progress bar
    const percentage = Math.round((completedCount / tasks.length) * 100);
    const percentageElement = document.getElementById('completion-percentage');
    const progressBar = document.getElementById('progress-bar');
    
    if (percentageElement) percentageElement.textContent = `${percentage}%`;
    if (progressBar) progressBar.style.width = `${percentage}%`;
  }

  // Check if module is complete and unlock next city
  function checkModuleCompletion() {
    const allTasks = Object.values(window.taskProgress);
    const isComplete = allTasks.every(task => task === true);
    
    if (isComplete) {
      const notification = document.getElementById('unlockNotification');
      if (notification) {
        notification.style.display = 'block';
        setTimeout(() => notification.style.display = 'none', 4000);
      }
      unlockNextCity();
      console.log('🎉 San Francisco module completed! Portland should now be unlocked.');
    }
  }

  // Fallback unlock methods
  function unlockNextCity() {
    try {
      const saved = localStorage.getItem('mchopiee_city_progress');
      let gameProgress = saved ? JSON.parse(saved) : { unlockedCities:[0,1,2], completedCities:[], totalCitiesCompleted:0 };
      if (!gameProgress.completedCities.includes(2)) {
        gameProgress.completedCities.push(2);
        gameProgress.totalCitiesCompleted++;
      }
      if (!gameProgress.unlockedCities.includes(3)) {
        gameProgress.unlockedCities.push(3);
      }
      localStorage.setItem('mchopiee_city_progress', JSON.stringify(gameProgress));
      console.log('✅ Progress updated:', gameProgress);
    } catch (e) {
      console.error('Unlock failed:', e);
    }
  }

  window.logTo = function (id, ...parts) {
    const el = document.getElementById(id);
    if (!el) return;
    const text = parts.map(p => typeof p === 'object' ? JSON.stringify(p, null, 2) : String(p)).join(' ');
    el.textContent += (el.textContent ? '\n' : '') + text;
    el.scrollTop = el.scrollHeight;
  };

  window.clearTerm = function (id) { const el = document.getElementById(id); if (el) el.textContent = ''; };

  // mock DB wrapper persisted to localStorage
  class MockDB {
    constructor() {
      this.load();
    }
    load() {
      const raw = localStorage.getItem('foodquest_sf_db_v1');
      if (raw) {
        const parsed = JSON.parse(raw);
        this.dishes = parsed.dishes || [];
        this.ingredients = parsed.ingredients || [];
        this.dishIngredients = parsed.dishIngredients || [];
      } else {
        this.dishes = [];
        this.ingredients = [];
        this.dishIngredients = [];
      }
    }
    save() {
      localStorage.setItem('foodquest_sf_db_v1', JSON.stringify({
        dishes: this.dishes, ingredients: this.ingredients, dishIngredients: this.dishIngredients
      }));
    }
    reset() {
      this.dishes = []; this.ingredients = []; this.dishIngredients = []; this.save();
    }
  }

  // API simulating atomic update with transaction-like rollback
  class MockAPI {
    constructor() {
      this.db = new MockDB();
    }

    _cloneState() {
      return {
        dishes: JSON.parse(JSON.stringify(this.db.dishes)),
        ingredients: JSON.parse(JSON.stringify(this.db.ingredients)),
        dishIngredients: JSON.parse(JSON.stringify(this.db.dishIngredients)),
      };
    }

    _restoreState(state) {
      this.db.dishes = state.dishes;
      this.db.ingredients = state.ingredients;
      this.db.dishIngredients = state.dishIngredients;
      this.db.save();
    }

    // findOrCreateIngredient by name (case-insensitive)
    findOrCreateIngredient(name) {
      const existing = this.db.ingredients.find(i => i.name.toLowerCase() === name.toLowerCase());
      if (existing) return existing;
      const newIng = { id: t(), name, createdAt: new Date().toISOString() };
      this.db.ingredients.push(newIng);
      return newIng;
    }

    // Simulates PUT /api/dishes/{id}
    async putDish(id, payload) {
      // server-side validation
      if (!payload || !payload.name || !payload.category || !Array.isArray(payload.ingredients) || isNaN(payload.calories)) {
        return { status: 400, body: { error: "Missing required fields" } };
      }

      const dishIndex = this.db.dishes.findIndex(d => d.id === id);
      if (dishIndex === -1) {
        return { status: 404, body: { error: "Dish not found" } };
      }

      // transaction simulation
      const before = this._cloneState();
      try {
        const dish = { ...this.db.dishes[dishIndex], ...payload, updatedAt: new Date().toISOString() };
        this.db.dishes[dishIndex] = dish;

        // remove old dish ingredients
        this.db.dishIngredients = this.db.dishIngredients.filter(di => di.dishId !== id);

        // create ingredients if missing, add dishIngredients
        for (const ing of payload.ingredients) {
          if (!ing || !ing.name) throw new Error("Invalid ingredient");
          const ingRec = this.findOrCreateIngredient(ing.name);
          this.db.dishIngredients.push({ id: t(), dishId: dish.id, ingredientId: ingRec.id, qty: ing.qty || null, unit: ing.unit || null });
        }

        // save and return updated resource
        this.db.save();
        return { status: 200, body: dish };
      } catch (err) {
        // rollback
        this._restoreState(before);
        return { status: 500, body: { error: err.message || "Transaction failed" } };
      }
    }

    // Bulk PUT
    async putBulk(updates) {
      if (!Array.isArray(updates)) return { status: 400, body: { error: "Expected array" } };
      const updated = [];
      for (const u of updates) {
        if (!u.id) return { status: 400, body: { error: "Missing id in update" } };
        const payload = Object.assign({ ingredients: [] }, u);
        const res = await this.putDish(u.id, payload);
        if (res.status !== 200) { return { status: 500, body: { error: "Bulk update failed" } }; }
        updated.push(res.body);
      }
      return { status: 200, body: updated };
    }

    // GET /api/dishes?city=sf
    async getDishes(query = {}) {
      const city = (query.city || 'sf').toLowerCase();
      return this.db.dishes.filter(d => (d.city || 'sf').toLowerCase() === city);
    }

    // reset
    reset() { this.db.reset(); }
  }

  // singleton
  window.MockAPIInstance = new MockAPI();

  // expose initializer
  window.initMock = function() {
    window.MockAPIInstance.reset();
    window.logTo('terminal-init', '[MockAPI] Reset DB. You can seed or update dishes now.');
    showToast("Mock DB reset");
  };

  // toast helper
  window.showToast = function(text, ms = 3000) {
    const b = document.getElementById('sqToast');
    b.textContent = text;
    b.style.display = 'block';
    setTimeout(()=> b.style.display = 'none', ms);
  };

  // initialize on load
  if (!localStorage.getItem('foodquest_sf_db_v1')) {
    window.MockAPIInstance.db.save();
    window.logTo('terminal-init', '[MockAPI] Initialized new DB. Try seeding!');
  } else {
    window.logTo('terminal-init', '[MockAPI] DB loaded from localStorage.');
  }
})();
</script>

---

# %% Interactive Task: DimSum Menu (Editable + Run)

<div class="sq-card">
  <div class="sq-label">Implement the <strong>DimSumMenu</strong> class with update methods <code>updatePrice()</code>, <code>updateDescription()</code>, <code>addOption()</code>, <code>removeOption()</code>.</div>

  <textarea id="code-dimsum" class="code-editor">
// class DimSumMenu implementation
class DimSumMenu {
  constructor(id, name, options = []) {
    this.id = id;
    this.name = name;
    this.options = options;
  }

  updatePrice(itemId, newPrice) {
    const item = this.options.find(o => o.id === itemId);
    if (item) item.price = newPrice;
  }

  updateDescription(itemId, newDesc) {
    const item = this.options.find(o => o.id === itemId);
    if (item) item.description = newDesc;
  }

  addOption(option) {
    this.options.push(option);
  }

  removeOption(itemId) {
    const index = this.options.findIndex(o => o.id === itemId);
    if (index > -1) this.options.splice(index, 1);
  }
}

// example usage
const menu = new DimSumMenu("m1", "Lunch Special");
menu.addOption({ id: "d1", name: "Har Gow", price: 6.99 });
menu.addOption({ id: "d2", name: "Siu Mai", price: 5.99 });
console.log("Initial menu:", menu);

menu.updatePrice("d1", 7.99);
menu.updateDescription("d2", "Pork & shrimp dumplings");
console.log("Updated menu:", menu);

completeTask('dimsum'); // Mark task as complete
  </textarea>

  <div style="margin-top:0.5rem">
    <button class="sq-btn sq-run" onclick="runEditor('code-dimsum','terminal-dimsum')">Run</button>
    <button class="sq-btn" onclick="copyEditor('code-dimsum')">Copy</button>
  </div>

  <pre id="terminal-dimsum" class="sq-terminal"></pre>
</div>

# %% Interactive Task: ChowmeinOrder (Editable + Run)

<div class="sq-card">
  <div class="sq-label">Implement <strong>ChowmeinOrder</strong> with update methods <code>updateProtein()</code>, <code>updateNoodleType()</code>, <code>updateSpiceLevel()</code>, <code>updateExtras()</code>.</div>

  <textarea id="code-chowmein" class="code-editor">
// ChowmeinOrder implementation
class ChowmeinOrder {
  constructor(id, protein, noodleType) {
    this.id = id;
    this.protein = protein;
    this.noodleType = noodleType;
    this.spiceLevel = "Medium";
    this.extras = [];
  }

  updateProtein(newProtein) { 
    this.protein = newProtein; 
    console.log(`Updated protein to ${newProtein}`);
  }

  updateNoodleType(newType) { 
    this.noodleType = newType;
    console.log(`Updated noodle type to ${newType}`);
  }

  updateSpiceLevel(level) {
    this.spiceLevel = level;
    console.log(`Updated spice level to ${level}`);
  }

  updateExtras(newExtras) {
    this.extras = newExtras;
    console.log(`Updated extras to ${newExtras.join(", ")}`);
  }
}

// example usage
const order = new ChowmeinOrder("c1", "Chicken", "Egg Noodles");
console.log("Initial order:", order);

order.updateProtein("Shrimp");
order.updateSpiceLevel("Hot");
order.updateExtras(["Bean Sprouts", "Green Onions"]);
console.log("Updated order:", order);

completeTask('chowmein'); // Mark task as complete
  </textarea>

  <div style="margin-top:0.5rem">
    <button class="sq-btn sq-run" onclick="runEditor('code-chowmein','terminal-chowmein')">Run</button>
    <button class="sq-btn" onclick="copyEditor('code-chowmein')">Copy</button>
  </div>

  <pre id="terminal-chowmein" class="sq-terminal"></pre>
</div>

# %% Interactive Task: Update the Sourdough (Form + Run)

<div class="sq-card">
  <div class="sq-label">Use the form to update a <strong>Sourdough</strong>. Required fields: <em>id, name, category, ingredients (name, qty, unit), calories</em>. Photo may be a URL or uploaded file (stored as data URL).</div>

  <div style="display:grid; grid-template-columns: 1fr; gap:0.5rem;">
    <label class="sq-label">Dish ID to update</label>
    <input id="dish-id" class="sq-field" placeholder="d123" />

    <label class="sq-label">Updated name</label>
    <input id="dish-name" class="sq-field" placeholder="Sourdough" value="SF Sourdough" />

    <label class="sq-label">Updated category</label>
    <input id="dish-category" class="sq-field" placeholder="Bread" value="Artisan Bread" />

    <label class="sq-label">Updated calories</label>
    <input id="dish-calories" type="number" class="sq-field" placeholder="180" value="180" />

    <label class="sq-label">Updated photo URL (optional)</label>
    <input id="dish-photo" class="sq-field" placeholder="https://..." />

    <label class="sq-label">Update Ingredients (name, qty, unit)</label>
    <div style="display:flex; gap:0.5rem;">
      <input id="ing-name" class="sq-field" placeholder="flour" />
      <input id="ing-qty" class="sq-field" placeholder="3" />
      <input id="ing-unit" class="sq-field" placeholder="cups" />
      <button class="sq-btn" onclick="addIngredient()">Add</button>
    </div>

    <div id="ingredients-list" class="small" style="margin-top:0.5rem">No ingredients yet</div>

    <div style="display:flex; gap:0.5rem; margin-top:0.75rem;">
      <button class="sq-btn sq-run" onclick="runUpdateForm()">Update Dish (PUT)</button>
      <button class="sq-btn" onclick="clearForm()">Clear</button>
    </div>

    <div style="margin-top:0.5rem">
      <div id="terminal-update" class="sq-terminal"></div>
    </div>
  </div>
</div>

<script>
(function(){
  window._localIngredientBuffer = [];
  window.addIngredient = function() {
    const name = document.getElementById('ing-name').value.trim();
    const qty = document.getElementById('ing-qty').value.trim();
    const unit = document.getElementById('ing-unit').value.trim();
    if (!name) { alert('Ingredient name required'); return; }
    window._localIngredientBuffer.push({ name, qty: qty || null, unit: unit || null });
    document.getElementById('ing-name').value = '';
    document.getElementById('ing-qty').value = '';
    document.getElementById('ing-unit').value = '';
    renderIngredientList();
  };

  window.renderIngredientList = function() {
    const el = document.getElementById('ingredients-list');
    if (!window._localIngredientBuffer.length) { el.textContent = 'No ingredients yet'; return; }
    el.innerHTML = window._localIngredientBuffer.map((ing,i) => `${i+1}. ${ing.name} — ${ing.qty||''} ${ing.unit||''} <button onclick="removeIngredient(${i})" style="margin-left:0.5rem">remove</button>`).join('<br>');
  };

  window.removeIngredient = function(i) { window._localIngredientBuffer.splice(i,1); renderIngredientList(); };

  window.clearForm = function() {
    document.getElementById('dish-id').value = '';
    document.getElementById('dish-name').value = '';
    document.getElementById('dish-category').value = '';
    document.getElementById('dish-calories').value = '';
    document.getElementById('dish-photo').value = '';
    window._localIngredientBuffer = [];
    renderIngredientList();
    clearTerm('terminal-update');
  };

  window.runUpdateForm = async function() {
    clearTerm('terminal-update');
    const id = document.getElementById('dish-id').value.trim();
    const name = document.getElementById('dish-name').value.trim();
    const category = document.getElementById('dish-category').value.trim();
    const calories = parseInt(document.getElementById('dish-calories').value);
    const photo = document.getElementById('dish-photo').value.trim() || null;
    const ingredients = window._localIngredientBuffer.slice();

    // client-side validation
    if (!id || !name || !category || isNaN(calories) || !ingredients.length) {
      logTo('terminal-update', '[Client] Validation failed: id, name, category, calories, and at least 1 ingredient required');
      return;
    }

    const payload = { name, category, calories, photo, ingredients, city: 'sf' };

    logTo('terminal-update', '[Client] Sending PUT /api/dishes/' + id, payload);

    // call mock API
    const res = await window.MockAPIInstance.putDish(id, payload);
    if (res.status === 200) {
      logTo('terminal-update', '[Server] 200 OK', res.body);
      showToast(res.body.name + ' updated — +50 XP');
    } else {
      logTo('terminal-update', '[Server] Error', res);
    }
  };
})();
</script>

# %% Interactive: Simulated PUT endpoint + Unit Test

<div class="sq-card">
  <div class="sq-label">Simulate a `PUT /api/dishes/{id}` call programmatically (JS). There is also a simple unit test runner below to assert `200` and returned resource.</div>

  <textarea id="code-put" class="code-editor">
// Example programmatic PUT using MockAPIInstance
(async function(){
  const id = "d123"; // must exist
  const payload = {
    name: "Garlic Noodles",
    category: "Noodles",
    calories: 550,
    photo: null,
    ingredients: [
      { name: "noodles", qty: "8", unit: "oz" },
      { name: "garlic", qty: "6", unit: "cloves" },
      { name: "butter", qty: "2", unit: "tbsp" }
    ],
    city: "sf"
  };

  const res = await window.MockAPIInstance.putDish(id, payload);
  console.log("Status:", res.status);
  console.log("Body:", res.body);
})();
  </textarea>

  <div style="margin-top:0.5rem">
    <button class="sq-btn sq-run" onclick="runEditor('code-put','terminal-put')">Run</button>
    <button class="sq-btn" onclick="copyEditor('code-put')">Copy</button>
  </div>

  <pre id="terminal-put" class="sq-terminal"></pre>

  <div style="margin-top:0.75rem;">
    <button class="sq-btn sq-run" onclick="runUnitTest()">Run Unit Test: PUT returns 200 & updated resource</button>
    <div id="terminal-test" class="sq-terminal" style="margin-top:0.5rem"></div>
  </div>
</div>

<script>
window.runUnitTest = async function() {
  clearTerm('terminal-test');
  // first create a dish
  const createRes = await window.MockAPIInstance.postDish({
    name: "Test Dish",
    category: "Test",
    calories: 100,
    ingredients: [{ name: "test", qty: "1", unit: "unit" }],
    city: "sf"
  });
  if (createRes.status !== 201) {
    logTo('terminal-test', '❌ Setup Failed: Could not create test dish');
    return;
  }
// Now update it
  const id = createRes.body.id;
  const updateRes = await window.MockAPIInstance.putDish(id, {
    name: "Updated Test Dish",
    category: "Test",
    calories: 200,
    ingredients: [{ name: "test", qty: "2", unit: "units" }],
    city: "sf"
  });
  if (updateRes.status === 200 && updateRes.body && updateRes.body.name === "Updated Test Dish") {
    logTo('terminal-test', '✅ Unit Test Passed: PUT returned 200 and resource updated');
    logTo('terminal-test', JSON.stringify(updateRes.body, null, 2));
    completeTask('sourdough'); // Mark task as complete
  } else {
    logTo('terminal-test', '❌ Unit Test Failed', JSON.stringify(updateRes, null, 2));
  }
};
</script>

# %% Interactive Task: Seed Pantry (Initial Data)

<div class="sq-card">
  <div class="sq-label">Seed the San Francisco pantry with at least three dishes (Sourdough, Cioppino, Dim Sum)</div>

  <div style="display:flex; gap:0.5rem;">
    <button class="sq-btn sq-run" onclick="seedPantry()">Seed Pantry</button>
    <button class="sq-btn" onclick="clearTerm('terminal-seed')">Clear</button>
  </div>

  <pre id="terminal-seed" class="sq-terminal" style="margin-top:0.5rem"></pre>
</div>

<script>
window.seedPantry = async function() {
  clearTerm('terminal-seed');
  const seed = [
    { name: "Sourdough Bread", category: "Bread", calories: 180, ingredients: [{name:"flour", qty:"3", unit:"cups"}], city:'sf' },
    { name: "Cioppino", category: "Seafood", calories: 450, ingredients: [{name:"fish", qty:"1", unit:"lb"}], city:'sf' },
    { name: "Dim Sum", category: "Chinese", calories: 600, ingredients: [{name:"flour", qty:"2", unit:"cups"}], city:'sf' },
  ];
  logTo('terminal-seed', '[Client] Sending bulk seed...');
  const res = await window.MockAPIInstance.postBulk(seed);
  if (res.status === 201) {
    logTo('terminal-seed', '✅ Seed success:', res.body);
    completeTask('seed'); // Mark task as complete
  } else {
    logTo('terminal-seed', '❌ Seed failed', res);
  };
};
</script>

# %% Interactive Task: View Pantry (GET /api/dishes?city=sf)

<div class="sq-card">
  <div class="sq-label">View the San Francisco pantry (GET /api/dishes?city=sf)</div>

  <div style="display:flex; gap:0.5rem;">
    <button class="sq-btn sq-run" onclick="viewPantry()">View Pantry</button>
    <button class="sq-btn" onclick="clearTerm('terminal-pantry')">Clear</button>
  </div>

  <pre id="terminal-pantry" class="sq-terminal" style="margin-top:0.5rem"></pre>
</div>

<script>
window.viewPantry = async function() {
  clearTerm('terminal-pantry');
  const dishes = await window.MockAPIInstance.getDishes({ city: 'sf' });
  if (!dishes.length) {
    logTo('terminal-pantry','[Server] 200 OK — No dishes found for city=sf. Try seeding.');
    return;
  }
  logTo('terminal-pantry','[Server] 200 OK — Dishes for city=sf:');
  dishes.forEach(d => logTo('terminal-pantry', JSON.stringify(d, null, 2)));
  completeTask('view'); // Mark task as complete
};
</script>

---

## 🎉 Module Complete — San Francisco

Congratulations! You've successfully completed **CRUD: UPDATE** in San Francisco. All tasks — updating dim sum menu, chowmein orders, and the interactive pantry — are done. ✅  

Your **Sourdough** update earned you **+50 XP** and the **"First Update"** badge! 🏆  

The next city awaits: **Portland — DELETE module unlocked!** 🌲  
Click through to begin exploring **removing dishes and cleaning up records** in PDX.

<script>
/* utilities used by editors */
function runEditor(editorId, termId) {
  clearTerm(termId);
  const code = document.getElementById(editorId).value;
  // capture console
  const term = document.getElementById(termId);
  const originalConsole = window.console;
  const fakeConsole = {
    log: (...args) => { logTo(termId, ...args); },
    error: (...args) => { logTo(termId, 'ERROR:', ...args); },
    warn: (...args) => { logTo(termId, 'WARN:', ...args); },
  };
  try {
    window.console = fakeConsole;
    // eslint-disable-next-line no-new-func
    const fn = new Function(code);
    const result = fn();
    if (result && typeof result.then === 'function') {
      result.then(r => window.console.log('[Promise resolved]', r)).catch(e => window.console.error(e));
    }
  } catch (err) {
    logTo(termId, 'Exception:', err && err.stack ? err.stack : String(err));
  } finally {
    window.console = originalConsole;
  }
}

function copyEditor(editorId) {
  const code = document.getElementById(editorId).value;
  navigator.clipboard?.writeText(code).then(()=> alert('Code copied to clipboard'), ()=> alert('Copy failed — try selecting and Ctrl+C'));
}

// small helper used above
function clearTerm(id) { const el = document.getElementById(id); if (el) el.textContent = ''; }

/* Theme toggle: default to dark; remembers preference in localStorage */
(function(){
  const btn = document.getElementById('themeToggleBtn');
  const preferred = localStorage.getItem('sf_theme') || 'dark';
  if (preferred === 'light') document.body.classList.add('light');
  updateThemeButton();

  btn.addEventListener('click', () => {
    document.body.classList.toggle('light');
    localStorage.setItem('sf_theme', document.body.classList.contains('light') ? 'light' : 'dark');
    updateThemeButton();
  });

  function updateThemeButton(){
    if (document.body.classList.contains('light')) {
      btn.textContent = '☀️ Light';
      btn.title = 'Switch to dark mode';
    } else {
      btn.textContent = '🌙 Dark';
      btn.title = 'Switch to light mode';
    }
  }
})();
</script>