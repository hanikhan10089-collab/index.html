<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dark Tales - Horror Stories Collection</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Creepster&family=Nosifer&family=Inter:wght@300;400;500;600;700&display=swap');
        
        .horror-font {
            font-family: 'Creepster', cursive;
        }
        
        .title-font {
            font-family: 'Nosifer', cursive;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #0c0c0c 0%, #1a0a0a 50%, #2d1b1b 100%);
        }
        
        .story-card {
            transition: all 0.3s ease;
            background: linear-gradient(145deg, #1a1a1a, #0d0d0d);
            border: 1px solid #333;
        }
        
        .story-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(139, 0, 0, 0.3);
            border-color: #8b0000;
        }
        
        .blood-text {
            color: #8b0000;
            text-shadow: 0 0 10px rgba(139, 0, 0, 0.5);
        }
        
        .modal-backdrop {
            backdrop-filter: blur(5px);
            background: rgba(0, 0, 0, 0.8);
        }
        
        .floating-animation {
            animation: float 3s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .spooky-border {
            border-image: linear-gradient(45deg, #8b0000, #4a0000, #8b0000) 1;
        }
        
        .reading-mode {
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            color: #e0e0e0;
            line-height: 1.8;
        }
    </style>
</head>
<body class="min-h-screen text-white">
    <!-- Header -->
    <header class="bg-black bg-opacity-50 backdrop-blur-sm border-b border-red-900 sticky top-0 z-40">
        <div class="container mx-auto px-4 py-4">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-3">
                    <div class="floating-animation">
                        <span class="text-4xl">👻</span>
                    </div>
                    <h1 class="title-font text-3xl blood-text">Dark Tales</h1>
                </div>
                <button id="addStoryBtn" class="bg-red-800 hover:bg-red-700 text-white px-6 py-2 rounded-lg font-semibold transition-colors duration-200 flex items-center space-x-2">
                    <span>📝</span>
                    <span>Add Story</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto px-4 py-8">
        <!-- Welcome Section -->
        <div class="text-center mb-12">
            <h2 class="horror-font text-5xl blood-text mb-4">Welcome to the Darkness</h2>
            <p class="text-gray-300 text-lg max-w-2xl mx-auto">
                Share your most terrifying tales and explore the nightmares of others. 
                Each story holds secrets that will haunt your dreams...
            </p>
        </div>

        <!-- Stories Grid -->
        <div id="storiesContainer" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <!-- Sample Stories -->
            <div class="story-card rounded-lg p-6 fade-in">
                <div class="flex items-center justify-between mb-4">
                    <span class="text-red-400 text-sm">👁️ Sample Story</span>
                    <span class="text-gray-500 text-xs">2 min read</span>
                </div>
                <h3 class="text-xl font-bold mb-3 text-white">The Midnight Visitor</h3>
                <p class="text-gray-400 text-sm mb-4 line-clamp-3">
                    Every night at 3:33 AM, I hear the same three knocks on my door. 
                    But when I check, no one is ever there. Tonight, I decided to wait and watch...
                </p>
                <button class="read-story-btn w-full bg-gray-800 hover:bg-gray-700 text-white py-2 rounded transition-colors duration-200" 
                        data-title="The Midnight Visitor" 
                        data-content="Every night at 3:33 AM, I hear the same three knocks on my door. But when I check, no one is ever there. Tonight, I decided to wait and watch...\n\nI positioned myself by the window, curtains slightly parted, heart pounding in my chest. The clock ticked ominously toward the dreaded hour. 3:32... 3:33...\n\nKnock. Knock. Knock.\n\nBut this time, I saw something that made my blood run cold. There was no one at the door. The knocking was coming from inside my house.\n\nI turned around slowly, and there, standing in my hallway, was a figure I recognized. It was me. But this other me was pale, with hollow eyes and a twisted smile.\n\n'You've been ignoring my calls,' it whispered. 'But I've been waiting so patiently to meet you.'\n\nThat's when I realized the horrible truth. I had died three weeks ago in a car accident. The knocking wasn't someone trying to get in.\n\nIt was me, trying to get out.">
                    Read Story 📖
                </button>
            </div>

            <div class="story-card rounded-lg p-6 fade-in">
                <div class="flex items-center justify-between mb-4">
                    <span class="text-red-400 text-sm">👁️ Sample Story</span>
                    <span class="text-gray-500 text-xs">3 min read</span>
                </div>
                <h3 class="text-xl font-bold mb-3 text-white">The Last Photo</h3>
                <p class="text-gray-400 text-sm mb-4 line-clamp-3">
                    I found an old camera at a garage sale. The photos it takes show things that haven't happened yet. 
                    The last photo I took shows my own funeral...
                </p>
                <button class="read-story-btn w-full bg-gray-800 hover:bg-gray-700 text-white py-2 rounded transition-colors duration-200"
                        data-title="The Last Photo"
                        data-content="I found an old camera at a garage sale. The photos it takes show things that haven't happened yet. The last photo I took shows my own funeral...\n\nAt first, I thought it was just a coincidence. The camera captured my neighbor's dog getting hit by a car - two days before it actually happened. Then it showed my sister's pregnancy announcement, weeks before she even knew.\n\nBut the photos kept getting darker. A house fire. A missing child. A car accident. All of them came true, exactly as the camera predicted.\n\nI should have stopped taking pictures. But curiosity got the better of me.\n\nThe final photo I took was of myself, holding the camera up to a mirror. But in the reflection, I wasn't alone. Behind me stood a tall, dark figure with no face.\n\nAnd in the photo, I was lying in a coffin.\n\nThe timestamp on the photo shows tomorrow's date. I've tried to destroy the camera, but it keeps reappearing on my nightstand.\n\nI can hear footsteps behind me now, even though I'm alone. The faceless figure from the photo is coming.\n\nAnd I know there's no way to change what the camera has already seen.">
                    Read Story 📖
                </button>
            </div>
        </div>

        <!-- Empty State -->
        <div id="emptyState" class="text-center py-16 hidden">
            <div class="text-6xl mb-4">🕷️</div>
            <h3 class="text-2xl font-bold mb-2 text-gray-300">No Stories Yet</h3>
            <p class="text-gray-500 mb-6">The darkness awaits your first tale...</p>
            <button id="addFirstStoryBtn" class="bg-red-800 hover:bg-red-700 text-white px-8 py-3 rounded-lg font-semibold transition-colors duration-200">
                Write Your First Horror Story
            </button>
        </div>
    </main>

    <!-- Add Story Modal -->
    <div id="addStoryModal" class="fixed inset-0 modal-backdrop hidden z-50 flex items-center justify-center p-4">
        <div class="bg-gray-900 rounded-lg max-w-2xl w-full max-h-[90vh] overflow-y-auto border border-red-900">
            <div class="p-6">
                <div class="flex items-center justify-between mb-6">
                    <h2 class="text-2xl font-bold blood-text">📝 Add New Horror Story</h2>
                    <button id="closeModal" class="text-gray-400 hover:text-white text-2xl">&times;</button>
                </div>
                
                <form id="storyForm">
                    <div class="mb-4">
                        <label class="block text-sm font-medium mb-2">Story Title</label>
                        <input type="text" id="storyTitle" required 
                               class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-2 text-white focus:outline-none focus:ring-2 focus:ring-red-500"
                               placeholder="Enter a spine-chilling title...">
                    </div>
                    
                    <div class="mb-4">
                        <label class="block text-sm font-medium mb-2">Category</label>
                        <select id="storyCategory" 
                                class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-2 text-white focus:outline-none focus:ring-2 focus:ring-red-500">
                            <option value="👻 Supernatural">👻 Supernatural</option>
                            <option value="🔪 Slasher">🔪 Slasher</option>
                            <option value="🧠 Psychological">🧠 Psychological</option>
                            <option value="👹 Monster">👹 Monster</option>
                            <option value="🏚️ Haunted">🏚️ Haunted</option>
                            <option value="🌙 Cosmic Horror">🌙 Cosmic Horror</option>
                        </select>
                    </div>
                    
                    <div class="mb-6">
                        <label class="block text-sm font-medium mb-2">Your Story</label>
                        <textarea id="storyContent" required rows="12"
                                  class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-2 text-white focus:outline-none focus:ring-2 focus:ring-red-500 resize-none"
                                  placeholder="Write your terrifying tale here... Make it as scary as you dare!"></textarea>
                        <div class="text-right text-sm text-gray-500 mt-1">
                            <span id="wordCount">0</span> words
                        </div>
                    </div>
                    
                    <div class="flex space-x-4">
                        <button type="submit" class="flex-1 bg-red-800 hover:bg-red-700 text-white py-3 rounded-lg font-semibold transition-colors duration-200">
                            Publish Story 🕯️
                        </button>
                        <button type="button" id="cancelBtn" class="flex-1 bg-gray-700 hover:bg-gray-600 text-white py-3 rounded-lg font-semibold transition-colors duration-200">
                            Cancel
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <!-- Read Story Modal -->
    <div id="readStoryModal" class="fixed inset-0 modal-backdrop hidden z-50 flex items-center justify-center p-4">
        <div class="reading-mode rounded-lg max-w-4xl w-full max-h-[90vh] overflow-y-auto border border-red-900">
            <div class="p-8">
                <div class="flex items-center justify-between mb-6">
                    <h2 id="readStoryTitle" class="text-3xl font-bold blood-text"></h2>
                    <button id="closeReadModal" class="text-gray-400 hover:text-white text-2xl">&times;</button>
                </div>
                
                <div id="readStoryContent" class="prose prose-invert max-w-none text-lg leading-relaxed whitespace-pre-line">
                </div>
                
                <div class="mt-8 pt-6 border-t border-gray-700">
                    <button id="closeReadStoryBtn" class="bg-red-800 hover:bg-red-700 text-white px-6 py-2 rounded-lg font-semibold transition-colors duration-200">
                        Close Story 📚
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Story management
        let stories = JSON.parse(localStorage.getItem('horrorStories')) || [];

        // DOM elements
        const addStoryBtn = document.getElementById('addStoryBtn');
        const addFirstStoryBtn = document.getElementById('addFirstStoryBtn');
        const addStoryModal = document.getElementById('addStoryModal');
        const readStoryModal = document.getElementById('readStoryModal');
        const closeModal = document.getElementById('closeModal');
        const closeReadModal = document.getElementById('closeReadModal');
        const closeReadStoryBtn = document.getElementById('closeReadStoryBtn');
        const cancelBtn = document.getElementById('cancelBtn');
        const storyForm = document.getElementById('storyForm');
        const storiesContainer = document.getElementById('storiesContainer');
        const emptyState = document.getElementById('emptyState');
        const wordCount = document.getElementById('wordCount');
        const storyContent = document.getElementById('storyContent');

        // Event listeners
        addStoryBtn.addEventListener('click', openAddModal);
        addFirstStoryBtn.addEventListener('click', openAddModal);
        closeModal.addEventListener('click', closeAddModal);
        closeReadModal.addEventListener('click', closeReadStoryModal);
        closeReadStoryBtn.addEventListener('click', closeReadStoryModal);
        cancelBtn.addEventListener('click', closeAddModal);
        storyForm.addEventListener('submit', addStory);
        storyContent.addEventListener('input', updateWordCount);

        // Close modals when clicking backdrop
        addStoryModal.addEventListener('click', (e) => {
            if (e.target === addStoryModal) closeAddModal();
        });
        readStoryModal.addEventListener('click', (e) => {
            if (e.target === readStoryModal) closeReadStoryModal();
        });

        function openAddModal() {
            addStoryModal.classList.remove('hidden');
            document.getElementById('storyTitle').focus();
        }

        function closeAddModal() {
            addStoryModal.classList.add('hidden');
            storyForm.reset();
            updateWordCount();
        }

        function closeReadStoryModal() {
            readStoryModal.classList.add('hidden');
        }

        function updateWordCount() {
            const words = storyContent.value.trim().split(/\s+/).filter(word => word.length > 0);
            wordCount.textContent = words.length;
        }

        function addStory(e) {
            e.preventDefault();
            
            const title = document.getElementById('storyTitle').value.trim();
            const category = document.getElementById('storyCategory').value;
            const content = document.getElementById('storyContent').value.trim();
            
            if (!title || !content) return;

            const story = {
                id: Date.now(),
                title,
                category,
                content,
                dateAdded: new Date().toLocaleDateString(),
                readTime: Math.max(1, Math.ceil(content.split(' ').length / 200))
            };

            stories.unshift(story);
            localStorage.setItem('horrorStories', JSON.stringify(stories));
            
            closeAddModal();
            renderStories();
        }

        function deleteStory(id) {
            if (confirm('Are you sure you want to delete this story? This action cannot be undone.')) {
                stories = stories.filter(story => story.id !== id);
                localStorage.setItem('horrorStories', JSON.stringify(stories));
                renderStories();
            }
        }

        function readStory(title, content) {
            document.getElementById('readStoryTitle').textContent = title;
            document.getElementById('readStoryContent').textContent = content;
            readStoryModal.classList.remove('hidden');
        }

        function renderStories() {
            const userStories = stories.filter(story => story.id);
            
            if (userStories.length === 0) {
                // Show sample stories only
                storiesContainer.innerHTML = `
                    <div class="story-card rounded-lg p-6 fade-in">
                        <div class="flex items-center justify-between mb-4">
                            <span class="text-red-400 text-sm">👁️ Sample Story</span>
                            <span class="text-gray-500 text-xs">2 min read</span>
                        </div>
                        <h3 class="text-xl font-bold mb-3 text-white">The Midnight Visitor</h3>
                        <p class="text-gray-400 text-sm mb-4">
                            Every night at 3:33 AM, I hear the same three knocks on my door. 
                            But when I check, no one is ever there. Tonight, I decided to wait and watch...
                        </p>
                        <button class="read-story-btn w-full bg-gray-800 hover:bg-gray-700 text-white py-2 rounded transition-colors duration-200" 
                                onclick="readStory('The Midnight Visitor', 'Every night at 3:33 AM, I hear the same three knocks on my door. But when I check, no one is ever there. Tonight, I decided to wait and watch...\\n\\nI positioned myself by the window, curtains slightly parted, heart pounding in my chest. The clock ticked ominously toward the dreaded hour. 3:32... 3:33...\\n\\nKnock. Knock. Knock.\\n\\nBut this time, I saw something that made my blood run cold. There was no one at the door. The knocking was coming from inside my house.\\n\\nI turned around slowly, and there, standing in my hallway, was a figure I recognized. It was me. But this other me was pale, with hollow eyes and a twisted smile.\\n\\n\\'You\\'ve been ignoring my calls,\\' it whispered. \\'But I\\'ve been waiting so patiently to meet you.\\'\\n\\nThat\\'s when I realized the horrible truth. I had died three weeks ago in a car accident. The knocking wasn\\'t someone trying to get in.\\n\\nIt was me, trying to get out.')">
                            Read Story 📖
                        </button>
                    </div>
                    <div class="story-card rounded-lg p-6 fade-in">
                        <div class="flex items-center justify-between mb-4">
                            <span class="text-red-400 text-sm">👁️ Sample Story</span>
                            <span class="text-gray-500 text-xs">3 min read</span>
                        </div>
                        <h3 class="text-xl font-bold mb-3 text-white">The Last Photo</h3>
                        <p class="text-gray-400 text-sm mb-4">
                            I found an old camera at a garage sale. The photos it takes show things that haven't happened yet. 
                            The last photo I took shows my own funeral...
                        </p>
                        <button class="read-story-btn w-full bg-gray-800 hover:bg-gray-700 text-white py-2 rounded transition-colors duration-200"
                                onclick="readStory('The Last Photo', 'I found an old camera at a garage sale. The photos it takes show things that haven\\'t happened yet. The last photo I took shows my own funeral...\\n\\nAt first, I thought it was just a coincidence. The camera captured my neighbor\\'s dog getting hit by a car - two days before it actually happened. Then it showed my sister\\'s pregnancy announcement, weeks before she even knew.\\n\\nBut the photos kept getting darker. A house fire. A missing child. A car accident. All of them came true, exactly as the camera predicted.\\n\\nI should have stopped taking pictures. But curiosity got the better of me.\\n\\nThe final photo I took was of myself, holding the camera up to a mirror. But in the reflection, I wasn\\'t alone. Behind me stood a tall, dark figure with no face.\\n\\nAnd in the photo, I was lying in a coffin.\\n\\nThe timestamp on the photo shows tomorrow\\'s date. I\\'ve tried to destroy the camera, but it keeps reappearing on my nightstand.\\n\\nI can hear footsteps behind me now, even though I\\'m alone. The faceless figure from the photo is coming.\\n\\nAnd I know there\\'s no way to change what the camera has already seen.')">
                            Read Story 📖
                        </button>
                    </div>
                `;
                return;
            }

            storiesContainer.innerHTML = userStories.map(story => `
                <div class="story-card rounded-lg p-6 fade-in">
                    <div class="flex items-center justify-between mb-4">
                        <span class="text-red-400 text-sm">${story.category}</span>
                        <div class="flex items-center space-x-2">
                            <span class="text-gray-500 text-xs">${story.readTime} min read</span>
                            <button onclick="deleteStory(${story.id})" class="text-red-500 hover:text-red-400 text-sm">🗑️</button>
                        </div>
                    </div>
                    <h3 class="text-xl font-bold mb-3 text-white">${story.title}</h3>
                    <p class="text-gray-400 text-sm mb-4">
                        ${story.content.substring(0, 150)}${story.content.length > 150 ? '...' : ''}
                    </p>
                    <div class="flex items-center justify-between">
                        <span class="text-gray-600 text-xs">Added ${story.dateAdded}</span>
                        <button onclick="readStory('${story.title.replace(/'/g, "\\'")}', '${story.content.replace(/'/g, "\\'").replace(/\n/g, '\\n')}')" 
                                class="bg-gray-800 hover:bg-gray-700 text-white px-4 py-2 rounded transition-colors duration-200">
                            Read Story 📖
                        </button>
                    </div>
                </div>
            `).join('');
        }

        // Initialize app
        renderStories();
        updateWordCount();
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'963bd599b0afc18d',t:'MTc1MzI4MDU5My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
