# openclaw-website<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OpenClaw - The AI That Actually Does Things</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome 图标 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- 自定义配置 -->
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        // OpenClaw 品牌色
                        primary: '#6366f1', // 主紫蓝色
                        secondary: '#10b981', // 辅助绿色
                        dark: '#111827',
                        light: '#f9fafb',
                        neutral: {
                            100: '#f3f4f6',
                            200: '#e5e7eb',
                            300: '#d1d5db',
                            700: '#374151',
                            800: '#1f2937',
                            900: '#111827',
                        }
                    },
                    fontFamily: {
                        inter: ['Inter', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    
    <style type="text/tailwindcss">
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
            .text-gradient {
                background-clip: text;
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
            }
            .bg-blur {
                backdrop-filter: blur(8px);
            }
        }
        
        /* 基础样式 */
        body {
            font-family: 'Inter', sans-serif;
        }
        
        /* 滚动条美化 */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: theme('colors.neutral.800');
        }
        ::-webkit-scrollbar-thumb {
            background: theme('colors.primary');
            border-radius: 4px;
        }
    </style>
</head>
<body class="bg-light dark:bg-dark text-neutral-800 dark:text-neutral-100 transition-colors duration-300">
    <!-- 导航栏 -->
    <nav class="fixed top-0 left-0 right-0 z-50 bg-white/80 dark:bg-dark/80 bg-blur border-b border-neutral-200 dark:border-neutral-700">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Logo -->
                <div class="flex items-center">
                    <a href="#" class="flex items-center gap-2 text-xl font-bold">
                        <i class="fa-solid fa-robot text-primary text-2xl"></i>
                        <span class="bg-gradient-to-r from-primary to-secondary text-gradient">OpenClaw</span>
                    </a>
                </div>
                
                <!-- 桌面端导航 -->
                <div class="hidden md:flex items-center gap-8">
                    <a href="#features" class="text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">Features</a>
                    <a href="#installation" class="text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">Install</a>
                    <a href="#integrations" class="text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">Integrations</a>
                    <a href="#faq" class="text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">FAQ</a>
                    <a href="https://github.com/openclaw" target="_blank" class="flex items-center gap-1 text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">
                        <i class="fa-brands fa-github"></i>
                        <span>GitHub</span>
                    </a>
                </div>
                
                <!-- 主题切换 + 移动端菜单按钮 -->
                <div class="flex items-center gap-4">
                    <button id="themeToggle" class="p-2 rounded-full hover:bg-neutral-200 dark:hover:bg-neutral-700 transition-colors">
                        <i class="fa-solid fa-sun light:hidden dark:inline-block"></i>
                        <i class="fa-solid fa-moon dark:hidden light:inline-block"></i>
                    </button>
                    
                    <!-- 移动端菜单按钮 -->
                    <button id="mobileMenuBtn" class="md:hidden p-2 rounded-full hover:bg-neutral-200 dark:hover:bg-neutral-700 transition-colors">
                        <i class="fa-solid fa-bars"></i>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- 移动端菜单 -->
        <div id="mobileMenu" class="md:hidden hidden bg-white dark:bg-neutral-800 border-b border-neutral-200 dark:border-neutral-700">
            <div class="container mx-auto px-4 py-3 flex flex-col gap-4">
                <a href="#features" class="py-2 text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">Features</a>
                <a href="#installation" class="py-2 text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">Install</a>
                <a href="#integrations" class="py-2 text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">Integrations</a>
                <a href="#faq" class="py-2 text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">FAQ</a>
                <a href="https://github.com/openclaw" target="_blank" class="py-2 flex items-center gap-1 text-neutral-700 dark:text-neutral-200 hover:text-primary dark:hover:text-primary transition-colors">
                    <i class="fa-brands fa-github"></i>
                    <span>GitHub</span>
                </a>
            </div>
        </div>
    </nav>

    <!-- 英雄区 -->
    <header class="pt-32 pb-20 md:pt-40 md:pb-28">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="max-w-4xl mx-auto text-center">
                <h1 class="text-4xl md:text-6xl font-bold mb-6 leading-tight">
                    The AI That <span class="bg-gradient-to-r from-primary to-secondary text-gradient">Actually Does Things</span>
                </h1>
                <p class="text-xl md:text-2xl text-neutral-700 dark:text-neutral-300 mb-10">
                    OpenClaw is your autonomous AI assistant that runs locally, accesses your entire system, 
                    and gets real work done—without sending your data to the cloud.
                </p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center">
                    <a href="#installation" class="bg-primary hover:bg-primary/90 text-white font-medium py-3 px-8 rounded-lg transition-colors shadow-lg hover:shadow-primary/30">
                        Get Started
                    </a>
                    <a href="https://github.com/openclaw" target="_blank" class="bg-white dark:bg-neutral-800 border border-neutral-300 dark:border-neutral-700 hover:bg-neutral-100 dark:hover:bg-neutral-700 text-neutral-800 dark:text-neutral-200 font-medium py-3 px-8 rounded-lg transition-colors flex items-center justify-center gap-2">
                        <i class="fa-brands fa-github"></i>
                        <span>View on GitHub</span>
                    </a>
                </div>
            </div>
            
            <!-- 英雄区图片 -->
            <div class="mt-16 max-w-5xl mx-auto">
                <div class="rounded-xl overflow-hidden shadow-2xl border border-neutral-200 dark:border-neutral-700">
                    <img src="https://picsum.photos/id/180/1200/600" alt="OpenClaw AI Assistant Interface" class="w-full h-auto">
                </div>
            </div>
            
            <!-- 信任标识 -->
            <div class="mt-16 text-center">
                <p class="text-sm text-neutral-500 dark:text-neutral-400 mb-6 uppercase tracking-wider">TRUSTED BY DEVELOPERS & TEAMS</p>
                <div class="flex flex-wrap justify-center gap-8 md:gap-16 items-center opacity-70">
                    <i class="fa-brands fa-python text-4xl"></i>
                    <i class="fa-brands fa-js text-4xl"></i>
                    <i class="fa-brands fa-docker text-4xl"></i>
                    <i class="fa-brands fa-linux text-4xl"></i>
                    <i class="fa-brands fa-windows text-4xl"></i>
                    <i class="fa-brands fa-apple text-4xl"></i>
                </div>
            </div>
        </div>
    </header>

    <main>
        <!-- 核心特性 -->
        <section id="features" class="py-20 bg-neutral-100 dark:bg-neutral-800/50">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-3xl mx-auto mb-16">
                    <h2 class="text-3xl md:text-4xl font-bold mb-6">Powerful Features</h2>
                    <p class="text-lg text-neutral-700 dark:text-neutral-300">
                        OpenClaw combines the power of large language models with full system access to automate your daily tasks.
                    </p>
                </div>
                
                <!-- 特性卡片 -->
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- 特性 1 -->
                    <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700 hover:shadow-lg transition-shadow">
                        <div class="w-12 h-12 bg-primary/10 dark:bg-primary/20 rounded-lg flex items-center justify-center mb-6">
                            <i class="fa-solid fa-shield-halved text-primary text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Runs Locally</h3>
                        <p class="text-neutral-700 dark:text-neutral-300">
                            All your data stays on your machine—no cloud uploads, no privacy concerns, full control over your AI.
                        </p>
                    </div>
                    
                    <!-- 特性 2 -->
                    <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700 hover:shadow-lg transition-shadow">
                        <div class="w-12 h-12 bg-primary/10 dark:bg-primary/20 rounded-lg flex items-center justify-center mb-6">
                            <i class="fa-solid fa-terminal text-primary text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Full System Access</h3>
                        <p class="text-neutral-700 dark:text-neutral-300">
                            Execute commands, read/write files, control browsers, and interact with any application on your system.
                        </p>
                    </div>
                    
                    <!-- 特性 3 -->
                    <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700 hover:shadow-lg transition-shadow">
                        <div class="w-12 h-12 bg-primary/10 dark:bg-primary/20 rounded-lg flex items-center justify-center mb-6">
                            <i class="fa-solid fa-brain text-primary text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Persistent Memory</h3>
                        <p class="text-neutral-700 dark:text-neutral-300">
                            Remembers your preferences, past interactions, and context to provide personalized assistance over time.
                        </p>
                    </div>
                    
                    <!-- 特性 4 -->
                    <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700 hover:shadow-lg transition-shadow">
                        <div class="w-12 h-12 bg-primary/10 dark:bg-primary/20 rounded-lg flex items-center justify-center mb-6">
                            <i class="fa-solid fa-comments text-primary text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Multi-Platform Chat</h3>
                        <p class="text-neutral-700 dark:text-neutral-300">
                            Control OpenClaw via WhatsApp, Telegram, Discord, Slack, and other messaging platforms.
                        </p>
                    </div>
                    
                    <!-- 特性 5 -->
                    <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700 hover:shadow-lg transition-shadow">
                        <div class="w-12 h-12 bg-primary/10 dark:bg-primary/20 rounded-lg flex items-center justify-center mb-6">
                            <i class="fa-solid fa-puzzle-piece text-primary text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Extensible Plugins</h3>
                        <p class="text-neutral-700 dark:text-neutral-300">
                            Add custom skills and integrations with the plugin system—build your own or use community-made plugins.
                        </p>
                    </div>
                    
                    <!-- 特性 6 -->
                    <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700 hover:shadow-lg transition-shadow">
                        <div class="w-12 h-12 bg-primary/10 dark:bg-primary/20 rounded-lg flex items-center justify-center mb-6">
                            <i class="fa-solid fa-cogs text-primary text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Model Agnostic</h3>
                        <p class="text-neutral-700 dark:text-neutral-300">
                            Works with GPT-4, Claude, Ollama, and other LLMs—switch between models based on your needs.
                        </p>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- 安装指南 -->
        <section id="installation" class="py-20">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="max-w-3xl mx-auto">
                    <div class="text-center mb-12">
                        <h2 class="text-3xl md:text-4xl font-bold mb-6">Get Started in Minutes</h2>
                        <p class="text-lg text-neutral-700 dark:text-neutral-300">
                            Install OpenClaw on your Mac, Windows, or Linux machine with just a few commands.
                        </p>
                    </div>
                    
                    <!-- 安装步骤 -->
                    <div class="space-y-8">
                        <!-- 步骤 1 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700">
                            <div class="flex items-start gap-4">
                                <div class="w-10 h-10 bg-primary text-white rounded-full flex items-center justify-center flex-shrink-0 font-bold">1</div>
                                <div>
                                    <h3 class="text-xl font-semibold mb-2">Prerequisites</h3>
                                    <p class="text-neutral-700 dark:text-neutral-300 mb-4">
                                        Make sure you have Python 3.10+ and pip installed on your system.
                                    </p>
                                    <div class="bg-neutral-100 dark:bg-neutral-900 rounded-lg p-4 font-mono text-sm overflow-x-auto">
                                        python --version<br>
                                        pip --version
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <!-- 步骤 2 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700">
                            <div class="flex items-start gap-4">
                                <div class="w-10 h-10 bg-primary text-white rounded-full flex items-center justify-center flex-shrink-0 font-bold">2</div>
                                <div>
                                    <h3 class="text-xl font-semibold mb-2">Install OpenClaw</h3>
                                    <p class="text-neutral-700 dark:text-neutral-300 mb-4">
                                        Install the OpenClaw package using pip:
                                    </p>
                                    <div class="bg-neutral-100 dark:bg-neutral-900 rounded-lg p-4 font-mono text-sm overflow-x-auto">
                                        pip install openclaw
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <!-- 步骤 3 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700">
                            <div class="flex items-start gap-4">
                                <div class="w-10 h-10 bg-primary text-white rounded-full flex items-center justify-center flex-shrink-0 font-bold">3</div>
                                <div>
                                    <h3 class="text-xl font-semibold mb-2">Configure Your API Keys</h3>
                                    <p class="text-neutral-700 dark:text-neutral-300 mb-4">
                                        Set up your LLM API keys (OpenAI, Anthropic, etc.):
                                    </p>
                                    <div class="bg-neutral-100 dark:bg-neutral-900 rounded-lg p-4 font-mono text-sm overflow-x-auto">
                                        openclaw configure
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <!-- 步骤 4 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700">
                            <div class="flex items-start gap-4">
                                <div class="w-10 h-10 bg-primary text-white rounded-full flex items-center justify-center flex-shrink-0 font-bold">4</div>
                                <div>
                                    <h3 class="text-xl font-semibold mb-2">Start the Assistant</h3>
                                    <p class="text-neutral-700 dark:text-neutral-300 mb-4">
                                        Launch OpenClaw and start using your AI assistant:
                                    </p>
                                    <div class="bg-neutral-100 dark:bg-neutral-900 rounded-lg p-4 font-mono text-sm overflow-x-auto">
                                        openclaw start
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- 替代安装方式 -->
                    <div class="mt-10 bg-neutral-100 dark:bg-neutral-800 rounded-xl p-6 border border-neutral-200 dark:border-neutral-700">
                        <h3 class="text-xl font-semibold mb-4">Alternative Installation Methods</h3>
                        <div class="space-y-4">
                            <div>
                                <p class="font-medium mb-2">Docker</p>
                                <div class="bg-neutral-200 dark:bg-neutral-900 rounded-lg p-4 font-mono text-sm overflow-x-auto">
                                    docker run -it --rm openclaw/openclaw
                                </div>
                            </div>
                            <div>
                                <p class="font-medium mb-2">From Source</p>
                                <div class="bg-neutral-200 dark:bg-neutral-900 rounded-lg p-4 font-mono text-sm overflow-x-auto">
                                    git clone https://github.com/openclaw/openclaw.git<br>
                                    cd openclaw<br>
                                    pip install -e .
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- 集成支持 -->
        <section id="integrations" class="py-20 bg-neutral-100 dark:bg-neutral-800/50">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-3xl mx-auto mb-16">
                    <h2 class="text-3xl md:text-4xl font-bold mb-6">Works With Your Tools</h2>
                    <p class="text-lg text-neutral-700 dark:text-neutral-300">
                        OpenClaw integrates with hundreds of applications and services to automate your workflow.
                    </p>
                </div>
                
                <!-- 集成图标网格 -->
                <div class="grid grid-cols-4 md:grid-cols-6 lg:grid-cols-8 gap-8 justify-items-center">
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-brands fa-whatsapp text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">WhatsApp</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-brands fa-telegram text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Telegram</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-brands fa-discord text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Discord</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-brands fa-slack text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Slack</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-solid fa-envelope text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Email</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-solid fa-calendar text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Calendar</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-brands fa-google text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Google</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-brands fa-microsoft text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Microsoft</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-solid fa-browser text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Browser</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-solid fa-file text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Files</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-solid fa-terminal text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">CLI</span>
                    </div>
                    <div class="flex flex-col items-center gap-2">
                        <i class="fa-solid fa-house-signal text-4xl text-neutral-700 dark:text-neutral-300"></i>
                        <span class="text-sm">Smart Home</span>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- FAQ -->
        <section id="faq" class="py-20">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="max-w-3xl mx-auto">
                    <div class="text-center mb-12">
                        <h2 class="text-3xl md:text-4xl font-bold mb-6">Frequently Asked Questions</h2>
                        <p class="text-lg text-neutral-700 dark:text-neutral-300">
                            Everything you need to know about OpenClaw.
                        </p>
                    </div>
                    
                    <!-- FAQ 折叠面板 -->
                    <div class="space-y-4">
                        <!-- FAQ 1 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl border border-neutral-200 dark:border-neutral-700 overflow-hidden">
                            <button class="faq-toggle w-full flex justify-between items-center p-6 text-left font-medium">
                                <span>Is my data safe with OpenClaw?</span>
                                <i class="fa-solid fa-chevron-down text-neutral-500 transition-transform duration-300"></i>
                            </button>
                            <div class="faq-content hidden px-6 pb-6">
                                <p class="text-neutral-700 dark:text-neutral-300">
                                    Yes! OpenClaw runs entirely on your local machine. No data is sent to the cloud unless you explicitly configure it to use cloud-based LLMs (like GPT-4). Even then, you can use local models (via Ollama) to keep all data on your device.
                                </p>
                            </div>
                        </div>
                        
                        <!-- FAQ 2 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl border border-neutral-200 dark:border-neutral-700 overflow-hidden">
                            <button class="faq-toggle w-full flex justify-between items-center p-6 text-left font-medium">
                                <span>What programming languages does OpenClaw support?</span>
                                <i class="fa-solid fa-chevron-down text-neutral-500 transition-transform duration-300"></i>
                            </button>
                            <div class="faq-content hidden px-6 pb-6">
                                <p class="text-neutral-700 dark:text-neutral-300">
                                    OpenClaw is built with Python, but it can execute commands and scripts in any language (Python, JavaScript, Bash, PowerShell, etc.). It can also interact with APIs and services regardless of the programming language they use.
                                </p>
                            </div>
                        </div>
                        
                        <!-- FAQ 3 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl border border-neutral-200 dark:border-neutral-700 overflow-hidden">
                            <button class="faq-toggle w-full flex justify-between items-center p-6 text-left font-medium">
                                <span>Can I use OpenClaw without an internet connection?</span>
                                <i class="fa-solid fa-chevron-down text-neutral-500 transition-transform duration-300"></i>
                            </button>
                            <div class="faq-content hidden px-6 pb-6">
                                <p class="text-neutral-700 dark:text-neutral-300">
                                    Yes! If you use local LLMs (via Ollama), OpenClaw can work completely offline. You'll only need internet access for cloud-based LLMs, external API integrations, or updating the software.
                                </p>
                            </div>
                        </div>
                        
                        <!-- FAQ 4 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl border border-neutral-200 dark:border-neutral-700 overflow-hidden">
                            <button class="faq-toggle w-full flex justify-between items-center p-6 text-left font-medium">
                                <span>How does OpenClaw compare to other AI assistants?</span>
                                <i class="fa-solid fa-chevron-down text-neutral-500 transition-transform duration-300"></i>
                            </button>
                            <div class="faq-content hidden px-6 pb-6">
                                <p class="text-neutral-700 dark:text-neutral-300">
                                    Unlike most AI assistants (ChatGPT, Bard, etc.), OpenClaw has direct access to your system and can perform real actions—not just generate text. It's autonomous, runs locally, and can be customized to fit your exact needs with plugins and custom scripts.
                                </p>
                            </div>
                        </div>
                        
                        <!-- FAQ 5 -->
                        <div class="bg-white dark:bg-neutral-800 rounded-xl border border-neutral-200 dark:border-neutral-700 overflow-hidden">
                            <button class="faq-toggle w-full flex justify-between items-center p-6 text-left font-medium">
                                <span>Is OpenClaw free to use?</span>
                                <i class="fa-solid fa-chevron-down text-neutral-500 transition-transform duration-300"></i>
                            </button>
                            <div class="faq-content hidden px-6 pb-6">
                                <p class="text-neutral-700 dark:text-neutral-300">
                                    Yes! OpenClaw is open source and free to use under the MIT license. You may incur costs for using cloud-based LLMs (like GPT-4 API calls), but the core software is completely free.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- 行动召唤 -->
        <section class="py-20 bg-gradient-to-r from-primary to-secondary text-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="max-w-3xl mx-auto text-center">
                    <h2 class="text-3xl md:text-4xl font-bold mb-6">Ready to Automate Your Workflow?</h2>
                    <p class="text-xl mb-8 text-white/90">
                        Join thousands of developers and power users who are using OpenClaw to get more done with less effort.
                    </p>
                    <div class="flex flex-col sm:flex-row gap-4 justify-center">
                        <a href="#installation" class="bg-white text-primary hover:bg-white/90 font-medium py-3 px-8 rounded-lg transition-colors shadow-lg hover:shadow-black/20">
                            Install Now
                        </a>
                        <a href="https://github.com/openclaw" target="_blank" class="bg-transparent border border-white hover:bg-white/10 text-white font-medium py-3 px-8 rounded-lg transition-colors flex items-center justify-center gap-2">
                            <i class="fa-brands fa-github"></i>
                            <span>Star on GitHub</span>
                        </a>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- 页脚 -->
    <footer class="bg-neutral-900 text-neutral-300 py-12">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid md:grid-cols-4 gap-8">
                <!-- 品牌信息 -->
                <div class="md:col-span-1">
                    <a href="#" class="flex items-center gap-2 text-xl font-bold mb-4">
                        <i class="fa-solid fa-robot text-primary text-2xl"></i>
                        <span class="text-white">OpenClaw</span>
                    </a>
                    <p class="text-sm text-neutral-400 mb-4">
                        The autonomous AI assistant that runs locally and gets real work done.
                    </p>
                    <div class="flex gap-4">
                        <a href="https://github.com/openclaw" target="_blank" class="text-neutral-400 hover:text-primary transition-colors">
                            <i class="fa-brands fa-github text-xl"></i>
                        </a>
                        <a href="#" class="text-neutral-400 hover:text-primary transition-colors">
                            <i class="fa-brands fa-twitter text-xl"></i>
                        </a>
                        <a href="#" class="text-neutral-400 hover:text-primary transition-colors">
                            <i class="fa-brands fa-discord text-xl"></i>
                        </a>
                        <a href="#" class="text-neutral-400 hover:text-primary transition-colors">
                            <i class="fa-brands fa-telegram text-xl"></i>
                        </a>
                    </div>
                </div>
                
                <!-- 链接 1 -->
                <div>
                    <h3 class="text-white font-medium mb-4">Product</h3>
                    <ul class="space-y-2 text-sm">
                        <li><a href="#features" class="text-neutral-400 hover:text-primary transition-colors">Features</a></li>
                        <li><a href="#integrations" class="text-neutral-400 hover:text-primary transition-colors">Integrations</a></li>
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">Roadmap</a></li>
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">Pricing</a></li>
                    </ul>
                </div>
                
                <!-- 链接 2 -->
                <div>
                    <h3 class="text-white font-medium mb-4">Resources</h3>
                    <ul class="space-y-2 text-sm">
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">Documentation</a></li>
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">API Reference</a></li>
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">Tutorials</a></li>
                        <li><a href="#faq" class="text-neutral-400 hover:text-primary transition-colors">FAQ</a></li>
                    </ul>
                </div>
                
                <!-- 链接 3 -->
                <div>
                    <h3 class="text-white font-medium mb-4">Company</h3>
                    <ul class="space-y-2 text-sm">
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">About</a></li>
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">Blog</a></li>
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">Contact</a></li>
                        <li><a href="#" class="text-neutral-400 hover:text-primary transition-colors">Privacy Policy</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="mt-12 pt-8 border-t border-neutral-800 text-center text-sm text-neutral-500">
                <p>© 2025 OpenClaw. All rights reserved. Open source under MIT License.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // 主题切换
        const themeToggle = document.getElementById('themeToggle');
        const html = document.documentElement;
        
        // 初始化主题
        if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
            html.classList.add('dark');
        } else {
            html.classList.remove('dark');
        }
        
        // 切换主题
        themeToggle.addEventListener('click', () => {
            html.classList.toggle('dark');
            if (html.classList.contains('dark')) {
                localStorage.theme = 'dark';
            } else {
                localStorage.theme = 'light';
            }
        });
        
        // 移动端菜单
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        
        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });
        
        // FAQ 折叠面板
        const faqToggles = document.querySelectorAll('.faq-toggle');
        
        faqToggles.forEach(toggle => {
            toggle.addEventListener('click', () => {
                const content = toggle.nextElementSibling;
                const icon = toggle.querySelector('i');
                
                // 切换当前面板
                content.classList.toggle('hidden');
                icon.classList.toggle('rotate-180');
                
                // 关闭其他面板
                faqToggles.forEach(otherToggle => {
                    if (otherToggle !== toggle) {
                        const otherContent = otherToggle.nextElementSibling;
                        const otherIcon = otherToggle.querySelector('i');
                        
                        if (!otherContent.classList.contains('hidden')) {
                            otherContent.classList.add('hidden');
                            otherIcon.classList.remove('rotate-180');
                        }
                    }
                });
            });
        });
        
        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    // 计算滚动位置（减去导航栏高度）
                    const navHeight = document.querySelector('nav').offsetHeight;
                    const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset - navHeight;
                    
                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                    
                    // 关闭移动端菜单
                    mobileMenu.classList.add('hidden');
                }
            });
        });
        
        // 滚动时导航栏效果
        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            if (window.scrollY > 10) {
                nav.classList.add('shadow-md');
            } else {
                nav.classList.remove('shadow-md');
            }
        });
    </script>
</body>
</html>
