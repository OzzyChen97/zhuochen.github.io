import React, { useState, useEffect } from 'react';
import { Github, Mail, Code, BookOpen, Terminal, Cpu, GraduationCap, ExternalLink, ChevronDown, Award, MapPin, Lock, Trophy } from 'lucide-react';

export default function Portfolio() {
  const [activeSection, setActiveSection] = useState('home');

  const scrollToSection = (id) => {
    const element = document.getElementById(id);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
      setActiveSection(id);
    }
  };

  // Nav items
  const navItems = [
    { id: 'about', label: 'About' },
    { id: 'experience', label: 'Experience' },
    { id: 'skills', label: 'Skills' },
    { id: 'projects', label: 'Projects' }, 
    { id: 'contact', label: 'Contact' },
  ];

  return (
    <div className="min-h-screen bg-slate-900 text-slate-200 font-sans selection:bg-teal-500 selection:text-white">
      {/* Navigation */}
      <nav className="fixed top-0 w-full bg-slate-900/90 backdrop-blur-sm z-50 border-b border-slate-800">
        <div className="max-w-5xl mx-auto px-6 py-4 flex justify-between items-center">
          <div className="text-xl font-bold bg-gradient-to-r from-teal-400 to-blue-500 bg-clip-text text-transparent cursor-pointer" onClick={() => scrollToSection('home')}>
            Ozzy.Math
          </div>
          <div className="hidden md:flex space-x-8">
            {navItems.map((item) => (
              <button
                key={item.id}
                onClick={() => scrollToSection(item.id)}
                className={`text-sm font-medium transition-colors hover:text-teal-400 ${
                  activeSection === item.id ? 'text-teal-400' : 'text-slate-400'
                }`}
              >
                {item.label}
              </button>
            ))}
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section id="home" className="min-h-screen flex items-center justify-center pt-16">
        <div className="max-w-4xl mx-auto px-6 text-center">
          <div className="mb-8 relative inline-block">
            <div className="absolute inset-0 bg-teal-500 blur-2xl opacity-20 rounded-full"></div>
            {/* TODO: 请将你的 Picture 1 (油画) 重命名为 avatar.jpg 并放入项目的 assets 文件夹中，
              或者直接替换下面的 src 链接。
            */}
            <img 
              src="./assets/avatar.jpg" 
              alt="Ozzy Chen Avatar" 
              className="w-40 h-40 rounded-full border-4 border-slate-800 shadow-xl relative z-10 object-cover mx-auto"
            />
          </div>
          
          <h1 className="text-5xl md:text-7xl font-bold mb-6 tracking-tight text-white">
            Hello, I'm <span className="text-teal-400">Ozzy Chen</span>
          </h1>
          
          <p className="text-xl md:text-2xl text-slate-400 max-w-2xl mx-auto leading-relaxed mb-8">
            Student at <span className="text-white">UNNC</span> | Mathematics & Applied Mathematics
            <br />
            Bridging <span className="text-teal-400">Math Theory</span> with <span className="text-blue-400">Programming</span>.
          </p>

          <div className="flex justify-center space-x-4 mb-12">
            <a href="https://github.com/OzzyChen97" target="_blank" rel="noreferrer" className="p-3 bg-slate-800 rounded-full hover:bg-slate-700 transition-colors hover:text-white text-slate-400">
              <Github size={24} />
            </a>
            <a href="mailto:comfortableapple@gmail.com" className="p-3 bg-slate-800 rounded-full hover:bg-slate-700 transition-colors hover:text-white text-slate-400">
              <Mail size={24} />
            </a>
          </div>

          <div className="animate-bounce cursor-pointer" onClick={() => scrollToSection('about')}>
            <ChevronDown className="mx-auto text-slate-500" size={32} />
          </div>
        </div>
      </section>

      {/* About & Photo */}
      <section id="about" className="py-20 bg-slate-800/50">
        <div className="max-w-5xl mx-auto px-6">
          <h2 className="text-3xl font-bold mb-12 flex items-center">
            <span className="text-teal-400 mr-2">01.</span> About Me
          </h2>
          
          <div className="grid md:grid-cols-2 gap-12 items-center">
            {/* Text Content */}
            <div className="space-y-6 text-lg text-slate-300 leading-relaxed order-2 md:order-1">
              <p>
                I am currently pursuing my degree in <strong>Mathematics & Applied Mathematics</strong> at the University of Nottingham Ningbo China (2024–2028).
              </p>
              <p>
                My passion lies in the intersection of rigorous mathematical theory and practical algorithmic implementation. I focus on <strong>algorithm optimization</strong> and finding quantitative solutions to complex problems using C++ and Python.
              </p>
              <blockquote className="border-l-4 border-teal-500 pl-4 italic text-slate-400 my-6 bg-slate-900/50 p-4 rounded-r">
                "Mathematics is the poetry of logical ideas" <br/>
                <span className="text-sm not-italic mt-2 block">— Albert Einstein</span>
              </blockquote>
            </div>

            {/* Photo Content (Replaced GitHub Stats) */}
            <div className="order-1 md:order-2 flex justify-center md:justify-end">
              <div className="relative group">
                <div className="absolute -inset-1 bg-gradient-to-r from-teal-500 to-blue-600 rounded-lg blur opacity-25 group-hover:opacity-75 transition duration-1000 group-hover:duration-200"></div>
                {/* TODO: 请将你的 Picture 2 (本人照片) 重命名为 profile.jpg 并放入项目的 assets 文件夹中，
                  或者直接替换下面的 src 链接。
                */}
                <img 
                  src="./assets/profile.jpg" 
                  alt="Ozzy Chen Profile" 
                  className="relative w-72 h-auto rounded-lg shadow-2xl border-2 border-slate-700/50 grayscale hover:grayscale-0 transition-all duration-500 object-cover"
                />
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Experience & Education */}
      <section id="experience" className="py-20">
        <div className="max-w-5xl mx-auto px-6">
          <h2 className="text-3xl font-bold mb-12 flex items-center">
            <span className="text-teal-400 mr-2">02.</span> Experience & Education
          </h2>

          <div className="relative border-l border-slate-700 ml-3 md:ml-6 space-y-12">
            
            {/* Research Item */}
            <div className="relative pl-8 md:pl-12">
              <div className="absolute -left-[9px] top-0 bg-slate-900 p-1 border border-teal-500 rounded-full">
                <Cpu size={16} className="text-teal-500" />
              </div>
              <div className="flex flex-col sm:flex-row sm:items-center sm:justify-between mb-2">
                <h3 className="text-xl font-bold text-white">Research Assistant</h3>
                <span className="text-sm font-mono text-teal-400">July 2025 – Present</span>
              </div>
              <div className="text-slate-400 mb-2 flex items-center gap-2">
                <MapPin size={14} /> Shenzhen University of Advanced Technology (AI Center)
              </div>
              <p className="text-slate-300 mb-4">
                Computer Vision and Recognition Center (AI觉-知研究中心)
              </p>
              <ul className="list-disc list-outside ml-4 text-slate-400 space-y-2 marker:text-teal-500">
                <li>Conducting research on <strong className="text-slate-200">Large Visual Language Models (LVLMs)</strong>, studying efficiency optimization.</li>
                <li>Investigating reasoning problems in long-context image understanding.</li>
                <li>Bridging sensory input with cognitive understanding using tools like Qwen2.5-VL.</li>
              </ul>
            </div>

            {/* Education Item */}
            <div className="relative pl-8 md:pl-12">
              <div className="absolute -left-[9px] top-0 bg-slate-900 p-1 border border-blue-500 rounded-full">
                <GraduationCap size={16} className="text-blue-500" />
              </div>
              <div className="flex flex-col sm:flex-row sm:items-center sm:justify-between mb-2">
                <h3 className="text-xl font-bold text-white">University of Nottingham Ningbo China</h3>
                <span className="text-sm font-mono text-blue-400">2024 – 2028</span>
              </div>
              <p className="text-slate-300">B.Sc. Mathematics & Applied Mathematics</p>
              <p className="text-slate-400 mt-2 text-sm">
                Relevant Coursework: Linear Algebra, Machine Learning, Deep Learning, Computer Vision.
              </p>
            </div>

          </div>
        </div>
      </section>

      {/* Skills */}
      <section id="skills" className="py-20 bg-slate-800/50">
        <div className="max-w-5xl mx-auto px-6">
          <h2 className="text-3xl font-bold mb-12 flex items-center">
            <span className="text-teal-400 mr-2">03.</span> Tech Stack
          </h2>
          
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {/* Languages */}
            <div className="bg-slate-900 p-6 rounded-xl border border-slate-700 hover:border-teal-500/50 transition-all">
              <div className="flex items-center gap-3 mb-6">
                <Terminal className="text-teal-400" />
                <h3 className="text-xl font-semibold text-white">Languages</h3>
              </div>
              <div className="space-y-4">
                <div>
                  <div className="flex justify-between text-sm mb-1">
                    <span>C++</span>
                    <span className="text-teal-400">Advanced</span>
                  </div>
                  <div className="h-2 bg-slate-700 rounded-full overflow-hidden">
                    <div className="h-full bg-teal-500 w-[90%]"></div>
                  </div>
                </div>
                <div>
                  <div className="flex justify-between text-sm mb-1">
                    <span>Python</span>
                    <span className="text-teal-400">Proficient</span>
                  </div>
                  <div className="h-2 bg-slate-700 rounded-full overflow-hidden">
                    <div className="h-full bg-blue-500 w-[80%]"></div>
                  </div>
                </div>
                <div>
                  <div className="flex justify-between text-sm mb-1">
                    <span>MATLAB / LaTeX</span>
                    <span className="text-teal-400">Academic</span>
                  </div>
                  <div className="h-2 bg-slate-700 rounded-full overflow-hidden">
                    <div className="h-full bg-purple-500 w-[75%]"></div>
                  </div>
                </div>
              </div>
            </div>

            {/* Tools */}
            <div className="bg-slate-900 p-6 rounded-xl border border-slate-700 hover:border-teal-500/50 transition-all">
              <div className="flex items-center gap-3 mb-6">
                <Code className="text-blue-400" />
                <h3 className="text-xl font-semibold text-white">Libraries & Tools</h3>
              </div>
              {/* Removed YOLOv8 as requested */}
              <div className="flex flex-wrap gap-2">
                {['PyTorch', 'Qwen2.5-VL', 'OpenCV', 'NumPy', 'Pandas', 'Git', 'Linux'].map((tool) => (
                  <span key={tool} className="px-3 py-1 bg-slate-800 text-slate-300 rounded-full text-sm border border-slate-700 hover:border-blue-400 hover:text-white transition-colors">
                    {tool}
                  </span>
                ))}
              </div>
            </div>

            {/* Domains */}
            <div className="bg-slate-900 p-6 rounded-xl border border-slate-700 hover:border-teal-500/50 transition-all">
              <div className="flex items-center gap-3 mb-6">
                <BookOpen className="text-purple-400" />
                <h3 className="text-xl font-semibold text-white">Domains</h3>
              </div>
              <ul className="space-y-3 text-slate-300">
                <li className="flex items-start gap-2">
                  <span className="text-teal-400 mt-1">▹</span> Large Visual Language Models
                </li>
                <li className="flex items-start gap-2">
                  <span className="text-teal-400 mt-1">▹</span> Algorithm Design
                </li>
                <li className="flex items-start gap-2">
                  <span className="text-teal-400 mt-1">▹</span> Data Structures
                </li>
                <li className="flex items-start gap-2">
                  <span className="text-teal-400 mt-1">▹</span> Mathematical Modeling
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      {/* Projects & Achievements */}
      <section id="projects" className="py-20">
        <div className="max-w-5xl mx-auto px-6">
          <h2 className="text-3xl font-bold mb-12 flex items-center">
            <span className="text-teal-400 mr-2">04.</span> Projects & Achievements
          </h2>
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            
            {/* MICCAI Paper Project */}
            <div className="bg-slate-800 p-6 rounded-lg hover:-translate-y-2 transition-transform duration-300 group border border-slate-700">
              <div className="flex justify-between items-start mb-4">
                <div className="text-teal-400"><Code size={32} /></div>
                <div className="flex gap-4">
                  <div className="flex items-center gap-1 text-xs text-amber-400 bg-amber-400/10 px-2 py-1 rounded border border-amber-400/20">
                    <Lock size={12} /> Private
                  </div>
                  <a href="https://github.com/OzzyChen97/moe" target="_blank" rel="noreferrer">
                    <Github className="text-slate-400 hover:text-white cursor-pointer" size={20} />
                  </a>
                </div>
              </div>
              <h3 className="text-xl font-bold text-white mb-2 group-hover:text-teal-400 transition-colors">LVLM Efficiency (MICCAI Prep)</h3>
              <p className="text-slate-400 mb-4 text-sm">
                Efficiency optimization for Large Visual Language Models using <strong>MoE (Mixture of Experts)</strong>. Addressing reasoning challenges in long-context medical/visual data.
              </p>
              <div className="flex flex-wrap gap-2 text-xs text-slate-500 font-mono mt-auto">
                <span>PyTorch</span>
                <span>MoE</span>
                <span>MICCAI'25</span>
              </div>
            </div>

            {/* Achievement: Young China Chip */}
            <div className="bg-slate-800 p-6 rounded-lg hover:-translate-y-2 transition-transform duration-300 group border border-slate-700">
              <div className="flex justify-between items-start mb-4">
                <div className="text-amber-400"><Trophy size={32} /></div>
                <div className="flex gap-4">
                  <ExternalLink className="text-slate-400 hover:text-white cursor-pointer" size={20} />
                </div>
              </div>
              <h3 className="text-xl font-bold text-white mb-2 group-hover:text-amber-400 transition-colors">Young China Chip Initiative</h3>
              <p className="text-slate-400 mb-4 text-sm">
                Awarded <strong>First Prize</strong> in this prestigious competition hosted by PKU, HKUST, and IEEE. Demonstrated excellence in hardware/algorithm co-design concepts.
              </p>
              <div className="flex flex-wrap gap-2 text-xs text-slate-500 font-mono mt-auto">
                <span>1st Prize</span>
                <span>IEEE</span>
                <span>Innovation</span>
              </div>
            </div>

            {/* Project: MCM Modeling (Renamed) */}
            <div className="bg-slate-800 p-6 rounded-lg hover:-translate-y-2 transition-transform duration-300 group border border-slate-700">
              <div className="flex justify-between items-start mb-4">
                <div className="text-blue-400"><Award size={32} /></div>
                <div className="flex gap-4">
                  {/* <Github className="text-slate-400 hover:text-white cursor-pointer" size={20} /> */}
                </div>
              </div>
              <h3 className="text-xl font-bold text-white mb-2 group-hover:text-blue-400 transition-colors">MCM Modeling</h3>
              <p className="text-slate-400 mb-4 text-sm">
                Participated in the Mathematical Contest in Modeling. Used differential equations and statistical analysis to model population growth under resource constraints.
              </p>
              <div className="flex flex-wrap gap-2 text-xs text-slate-500 font-mono mt-auto">
                <span>LaTeX</span>
                <span>NumPy</span>
                <span>Modeling</span>
              </div>
            </div>
          </div>

          <div className="mt-8 text-center">
            <p className="text-slate-500 italic text-sm">Also participated in NOI CCF-CSP & Kaggle Competitions.</p>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer id="contact" className="py-12 bg-slate-900 border-t border-slate-800 text-center">
        <h2 className="text-2xl font-bold text-white mb-6">Let's Connect</h2>
        <p className="text-slate-400 mb-8 max-w-md mx-auto">
          Whether you have a question about math, algorithms, or just want to say hi, my inbox is always open.
        </p>
        <a 
          href="mailto:comfortableapple@gmail.com" 
          className="inline-flex items-center gap-2 px-6 py-3 border border-teal-500 text-teal-400 rounded hover:bg-teal-500/10 transition-colors mb-12"
        >
          <Mail size={18} /> Say Hello
        </a>
        
        <div className="text-slate-600 text-sm">
          <p>&copy; {new Date().getFullYear()} Ozzy Chen. All rights reserved.</p>
          <p className="mt-2 text-xs">Built with React & Tailwind. Hosted on zhuochen.github.io</p>
        </div>
      </footer>
    </div>
  );
}
