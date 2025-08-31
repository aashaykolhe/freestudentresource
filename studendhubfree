import React, { useState, useMemo } from 'react';
import { Search, Plus, Download, ExternalLink, Video, FileText, Code, Star, Users, Filter, BookOpen, Play, Link2, Github, Map, Target, CheckCircle, ArrowRight, Calendar, Trophy } from 'lucide-react';

const ProgrammingResourceHub = () => {
  const [resources, setResources] = useState([
    // JavaScript Resources
    {
      id: 1, title: "JavaScript.info - Modern JavaScript Tutorial", type: "link", category: "JavaScript", language: "JavaScript",
      url: "https://javascript.info/", description: "Complete modern JavaScript tutorial from basics to advanced topics with examples and tasks",
      author: "Ilya Kantor", rating: 4.9, downloads: 45600
    },
    {
      id: 2, title: "MDN JavaScript Guide", type: "link", category: "JavaScript", language: "JavaScript",
      url: "https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide", description: "Mozilla's comprehensive JavaScript documentation and tutorials",
      author: "Mozilla", rating: 4.8, downloads: 89200
    },
    {
      id: 3, title: "Eloquent JavaScript (Free Book)", type: "pdf", category: "JavaScript", language: "JavaScript",
      url: "https://eloquentjavascript.net/", description: "Comprehensive JavaScript book covering syntax to advanced programming concepts",
      author: "Marijn Haverbeke", rating: 4.9, downloads: 167800
    },
    {
      id: 4, title: "JavaScript30 - 30 Day Challenge", type: "video", category: "JavaScript", language: "JavaScript",
      url: "https://javascript30.com/", description: "Build 30 projects in 30 days with vanilla JavaScript",
      author: "Wes Bos", rating: 4.8, downloads: 98400
    },
    {
      id: 5, title: "You Don't Know JS Book Series", type: "pdf", category: "JavaScript", language: "JavaScript",
      url: "https://github.com/getify/You-Dont-Know-JS", description: "Deep dive into JavaScript mechanisms and advanced concepts",
      author: "Kyle Simpson", rating: 4.9, downloads: 234700
    },

    // Python Resources
    {
      id: 6, title: "Python.org Official Tutorial", type: "link", category: "Python", language: "Python",
      url: "https://docs.python.org/3/tutorial/", description: "Official Python tutorial covering all language fundamentals",
      author: "Python Software Foundation", rating: 4.8, downloads: 189400
    },
    {
      id: 7, title: "Automate the Boring Stuff with Python", type: "pdf", category: "Python", language: "Python",
      url: "https://automatetheboringstuff.com/", description: "Free online book teaching Python through practical automation projects",
      author: "Al Sweigart", rating: 4.8, downloads: 278900
    },
    {
      id: 8, title: "Real Python Tutorials", type: "link", category: "Python", language: "Python",
      url: "https://realpython.com/", description: "In-depth Python tutorials for all skill levels with practical examples",
      author: "Real Python Team", rating: 4.9, downloads: 143200
    },
    {
      id: 9, title: "Python Crash Course Resources", type: "pdf", category: "Python", language: "Python",
      url: "https://ehmatthes.github.io/pcc_3e/", description: "Resources for Python Crash Course - hands-on introduction to programming",
      author: "Eric Matthes", rating: 4.7, downloads: 89600
    },
    {
      id: 10, title: "Corey Schafer Python Tutorials", type: "video", category: "Python", language: "Python",
      url: "https://www.youtube.com/c/Coreyms", description: "Complete Python video series from basics to advanced topics",
      author: "Corey Schafer", rating: 4.9, downloads: 192300
    },

    // Web Development Resources
    {
      id: 11, title: "freeCodeCamp Web Development Curriculum", type: "link", category: "Web Development", language: "JavaScript",
      url: "https://www.freecodecamp.org/learn", description: "Complete full-stack web development curriculum with certifications",
      author: "freeCodeCamp", rating: 4.9, downloads: 456700
    },
    {
      id: 12, title: "The Odin Project", type: "link", category: "Web Development", language: "JavaScript",
      url: "https://www.theodinproject.com/", description: "Free full-stack web development curriculum with hands-on projects",
      author: "The Odin Project", rating: 4.8, downloads: 167800
    },
    {
      id: 13, title: "MDN Web Development Learning Path", type: "link", category: "Web Development", language: "General",
      url: "https://developer.mozilla.org/en-US/docs/Learn", description: "Comprehensive web development tutorials from Mozilla",
      author: "Mozilla", rating: 4.8, downloads: 189200
    },
    {
      id: 14, title: "CSS-Tricks Complete Guide", type: "link", category: "Frontend", language: "CSS",
      url: "https://css-tricks.com/", description: "Tips, tricks, and techniques for modern CSS and web development",
      author: "CSS-Tricks", rating: 4.7, downloads: 145600
    },
    {
      id: 15, title: "Frontend Masters Learning Paths", type: "video", category: "Frontend", language: "JavaScript",
      url: "https://frontendmasters.com/learn/", description: "Professional front-end development courses and learning paths",
      author: "Frontend Masters", rating: 4.8, downloads: 78900
    },

    // React & Vue Resources  
    {
      id: 16, title: "React Official Documentation", type: "link", category: "Frontend", language: "JavaScript",
      url: "https://react.dev/", description: "Official React documentation with interactive tutorials",
      author: "Meta", rating: 4.8, downloads: 234500
    },
    {
      id: 17, title: "Vue.js Official Guide", type: "link", category: "Frontend", language: "JavaScript",
      url: "https://vuejs.org/guide/", description: "Comprehensive Vue.js documentation and tutorials",
      author: "Vue.js Team", rating: 4.7, downloads: 123400
    },
    {
      id: 18, title: "Scrimba React Course", type: "video", category: "Frontend", language: "JavaScript",
      url: "https://scrimba.com/learn/learnreact", description: "Interactive React course with hands-on coding exercises",
      author: "Scrimba", rating: 4.8, downloads: 89200
    },

    // Backend Development
    {
      id: 19, title: "Node.js Official Documentation", type: "link", category: "Backend", language: "JavaScript",
      url: "https://nodejs.org/en/docs/", description: "Complete Node.js documentation with guides and API reference",
      author: "Node.js Foundation", rating: 4.8, downloads: 223400
    },
    {
      id: 20, title: "Express.js Guide", type: "link", category: "Backend", language: "JavaScript",
      url: "https://expressjs.com/", description: "Fast, unopinionated web framework for Node.js",
      author: "Express.js Team", rating: 4.7, downloads: 189200
    },
    {
      id: 21, title: "Django Official Documentation", type: "link", category: "Backend", language: "Python",
      url: "https://docs.djangoproject.com/", description: "Complete Django web framework documentation and tutorials",
      author: "Django Software Foundation", rating: 4.8, downloads: 178900
    },
    {
      id: 22, title: "Flask Mega-Tutorial", type: "link", category: "Backend", language: "Python",
      url: "https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world", description: "Comprehensive Flask tutorial building a complete web application",
      author: "Miguel Grinberg", rating: 4.8, downloads: 67800
    },

    // Data Science & Machine Learning
    {
      id: 23, title: "Kaggle Learn Courses", type: "link", category: "Data Science", language: "Python",
      url: "https://www.kaggle.com/learn", description: "Free micro-courses in data science and machine learning",
      author: "Kaggle", rating: 4.8, downloads: 178400
    },
    {
      id: 24, title: "Andrew Ng Machine Learning Course", type: "video", category: "Data Science", language: "Python",
      url: "https://www.coursera.org/specializations/machine-learning-introduction", description: "Stanford's famous machine learning course by Andrew Ng",
      author: "Stanford University", rating: 4.9, downloads: 534500
    },
    {
      id: 25, title: "Python for Data Analysis Book", type: "pdf", category: "Data Science", language: "Python",
      url: "https://wesmckinney.com/book/", description: "Comprehensive guide to data analysis with pandas, NumPy, and matplotlib",
      author: "Wes McKinney", rating: 4.8, downloads: 189600
    },
    {
      id: 26, title: "Fast.ai Practical Deep Learning", type: "video", category: "Data Science", language: "Python",
      url: "https://course.fast.ai/", description: "Top-down approach to learning deep learning for coders",
      author: "fast.ai", rating: 4.9, downloads: 267800
    },
    {
      id: 27, title: "Google AI Education", type: "link", category: "Data Science", language: "Python",
      url: "https://ai.google/education/", description: "Free AI and machine learning courses from Google",
      author: "Google", rating: 4.7, downloads: 145600
    },

    // DevOps & Cloud
    {
      id: 28, title: "Docker Official Documentation", type: "link", category: "DevOps", language: "General",
      url: "https://docs.docker.com/", description: "Complete Docker containerization documentation and tutorials",
      author: "Docker Inc.", rating: 4.7, downloads: 334500
    },
    {
      id: 29, title: "Kubernetes Learning Path", type: "link", category: "DevOps", language: "General",
      url: "https://kubernetes.io/docs/tutorials/", description: "Official Kubernetes tutorials and learning resources",
      author: "Kubernetes", rating: 4.8, downloads: 234700
    },
    {
      id: 30, title: "AWS Free Training", type: "video", category: "DevOps", language: "General",
      url: "https://aws.amazon.com/training/free/", description: "Free AWS cloud computing training and certification prep",
      author: "Amazon Web Services", rating: 4.7, downloads: 456700
    },

    // Mobile Development
    {
      id: 31, title: "React Native Documentation", type: "link", category: "Mobile", language: "JavaScript",
      url: "https://reactnative.dev/", description: "Build mobile apps using React Native framework",
      author: "Meta", rating: 4.7, downloads: 256700
    },
    {
      id: 32, title: "Flutter Documentation", type: "link", category: "Mobile", language: "Dart",
      url: "https://docs.flutter.dev/", description: "Google's UI toolkit for building natively compiled applications",
      author: "Google", rating: 4.8, downloads: 378900
    },
    {
      id: 33, title: "Swift Programming Guide", type: "link", category: "Mobile", language: "Swift",
      url: "https://docs.swift.org/swift-book/", description: "Apple's official Swift programming language guide",
      author: "Apple", rating: 4.8, downloads: 167800
    },

    // System Design & Algorithms
    {
      id: 34, title: "System Design Primer", type: "link", category: "System Design", language: "General",
      url: "https://github.com/donnemartin/system-design-primer", description: "Learn how to design large-scale systems with examples",
      author: "Donne Martin", rating: 4.9, downloads: 656700
    },
    {
      id: 35, title: "LeetCode Practice Problems", type: "link", category: "Algorithms", language: "General",
      url: "https://leetcode.com/", description: "Coding interview problems and algorithmic challenges",
      author: "LeetCode", rating: 4.7, downloads: 445600
    },
    {
      id: 36, title: "JavaScript Algorithms Repository", type: "link", category: "Algorithms", language: "JavaScript",
      url: "https://github.com/trekhleb/javascript-algorithms", description: "JavaScript implementations of popular algorithms and data structures",
      author: "Oleksii Trekhleb", rating: 4.9, downloads: 334700
    },
    {
      id: 37, title: "MIT Introduction to Algorithms", type: "video", category: "Algorithms", language: "General",
      url: "https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-fall-2011/", description: "MIT's comprehensive algorithms course with video lectures",
      author: "MIT OpenCourseWare", rating: 4.9, downloads: 267800
    },

    // Additional Popular Resources
    {
      id: 38, title: "GitHub Student Developer Pack", type: "link", category: "General", language: "General",
      url: "https://education.github.com/pack", description: "Free developer tools and resources for students",
      author: "GitHub", rating: 4.8, downloads: 567800
    },
    {
      id: 39, title: "Codecademy Interactive Courses", type: "link", category: "General", language: "General",
      url: "https://www.codecademy.com/", description: "Interactive coding lessons in various programming languages",
      author: "Codecademy", rating: 4.7, downloads: 678900
    },
    {
      id: 40, title: "edX Computer Science Courses", type: "video", category: "General", language: "General",
      url: "https://www.edx.org/learn/computer-science", description: "University-level computer science courses from top institutions",
      author: "edX", rating: 4.8, downloads: 445600
    }
  ]);

  const [searchTerm, setSearchTerm] = useState('');
  const [selectedCategory, setSelectedCategory] = useState('All');
  const [showAddForm, setShowAddForm] = useState(false);
  const [activeTab, setActiveTab] = useState('resources');
  // Essential Student Sites - Must-know platforms for every programming student
  const essentialSites = [
    {
      name: "GitHub",
      url: "https://github.com",
      description: "Version control & code collaboration platform. Host your projects, contribute to open source, and showcase your portfolio.",
      category: "Development Tools",
      priority: "Critical"
    },
    {
      name: "Stack Overflow",
      url: "https://stackoverflow.com",
      description: "Programming Q&A community. Get help with coding problems and learn from millions of developer discussions.",
      category: "Community",
      priority: "Critical"
    },
    {
      name: "MDN Web Docs",
      url: "https://developer.mozilla.org",
      description: "Complete web development documentation. HTML, CSS, JavaScript references and tutorials from Mozilla.",
      category: "Documentation",
      priority: "Critical"
    },
    {
      name: "CodePen",
      url: "https://codepen.io",
      description: "Online code editor for frontend experiments. Test HTML, CSS, JS snippets and see live results instantly.",
      category: "Development Tools",
      priority: "High"
    },
    {
      name: "LeetCode",
      url: "https://leetcode.com",
      description: "Coding interview preparation platform. Practice algorithms and data structures for tech job interviews.",
      category: "Interview Prep",
      priority: "High"
    },
    {
      name: "HackerRank",
      url: "https://www.hackerrank.com",
      description: "Programming challenges and skill assessment. Improve coding skills across multiple languages and domains.",
      category: "Practice",
      priority: "High"
    },
    {
      name: "freeCodeCamp",
      url: "https://www.freecodecamp.org",
      description: "Free programming curriculum with certifications. Learn web development, data science, and more through projects.",
      category: "Learning",
      priority: "Critical"
    },
    {
      name: "Repl.it",
      url: "https://replit.com",
      description: "Online IDE supporting 50+ languages. Code, collaborate, and deploy projects directly from your browser.",
      category: "Development Tools",
      priority: "Medium"
    },
    {
      name: "Coursera",
      url: "https://www.coursera.org",
      description: "University-level courses from top institutions. Many programming and CS courses available for free audit.",
      category: "Learning",
      priority: "High"
    },
    {
      name: "edX",
      url: "https://www.edx.org",
      description: "Harvard, MIT, and other top university courses. Computer science and programming courses from world-class institutions.",
      category: "Learning",
      priority: "High"
    },
    {
      name: "VS Code",
      url: "https://code.visualstudio.com",
      description: "Most popular code editor. Free, powerful IDE with extensions for every programming language and framework.",
      category: "Development Tools",
      priority: "Critical"
    },
    {
      name: "Git",
      url: "https://git-scm.com",
      description: "Version control system. Essential tool for tracking code changes and collaborating with other developers.",
      category: "Development Tools",
      priority: "Critical"
    },
    {
      name: "Node.js",
      url: "https://nodejs.org",
      description: "JavaScript runtime for backend development. Run JavaScript outside the browser and build server applications.",
      category: "Runtime",
      priority: "High"
    },
    {
      name: "npm",
      url: "https://www.npmjs.com",
      description: "Node.js package manager. Access millions of JavaScript packages and libraries for your projects.",
      category: "Package Manager",
      priority: "High"
    },
    {
      name: "JSON Formatter",
      url: "https://jsonformatter.curiousconcept.com",
      description: "Format and validate JSON data. Essential tool for API development and data manipulation.",
      category: "Utilities",
      priority: "Medium"
    },
    {
      name: "RegExr",
      url: "https://regexr.com",
      description: "Regular expression testing tool. Learn and test regex patterns with real-time explanations.",
      category: "Utilities",
      priority: "Medium"
    },
    {
      name: "Can I Use",
      url: "https://caniuse.com",
      description: "Browser compatibility tables. Check which web features are supported across different browsers.",
      category: "Reference",
      priority: "High"
    },
    {
      name: "W3Schools",
      url: "https://www.w3schools.com",
      description: "Web development tutorials and references. Quick examples and syntax guides for HTML, CSS, JavaScript, and more.",
      category: "Learning",
      priority: "Medium"
    },
    {
      name: "Kaggle",
      url: "https://www.kaggle.com",
      description: "Data science platform. Datasets, competitions, and machine learning courses for data science students.",
      category: "Data Science",
      priority: "High"
    },
    {
      name: "Figma",
      url: "https://www.figma.com",
      description: "UI/UX design tool. Create mockups, prototypes, and collaborate on design projects for your applications.",
      category: "Design",
      priority: "Medium"
    },
    {
      name: "Postman",
      url: "https://www.postman.com",
      description: "API development and testing platform. Test REST APIs, document endpoints, and collaborate on API projects.",
      category: "API Tools",
      priority: "High"
    },
    {
      name: "Docker Hub",
      url: "https://hub.docker.com",
      description: "Container registry service. Find and share containerized applications and learn containerization.",
      category: "DevOps",
      priority: "Medium"
    },
    {
      name: "Heroku",
      url: "https://www.heroku.com",
      description: "Cloud application platform. Deploy and host your web applications easily with free tier options.",
      category: "Hosting",
      priority: "High"
    },
    {
      name: "Netlify",
      url: "https://www.netlify.com",
      description: "Static site hosting platform. Deploy frontend projects instantly with continuous deployment from Git.",
      category: "Hosting",
      priority: "High"
    }
  ];
  const [newResource, setNewResource] = useState({
    title: '', type: 'link', category: 'JavaScript', language: 'JavaScript', url: '', description: '', author: ''
  });

  // Learning Paths for Different Careers
  const learningPaths = {
    "Frontend Developer": {
      duration: "6-8 months",
      description: "Build beautiful, interactive user interfaces for web applications",
      skills: ["HTML/CSS", "JavaScript", "React/Vue", "Responsive Design", "Git/GitHub"],
      steps: [
        { title: "HTML & CSS Fundamentals", duration: "3-4 weeks", resources: ["MDN HTML Guide", "CSS-Tricks", "freeCodeCamp HTML/CSS"] },
        { title: "JavaScript Basics", duration: "6-8 weeks", resources: ["JavaScript.info", "JavaScript30", "MDN JavaScript Guide"] },
        { title: "React or Vue Framework", duration: "8-10 weeks", resources: ["React Documentation", "Scrimba React Course", "Vue.js Guide"] },
        { title: "Build Portfolio Projects", duration: "4-6 weeks", resources: ["Frontend Mentor", "Personal Projects", "GitHub Pages"] },
        { title: "Advanced Topics & Tools", duration: "4-6 weeks", resources: ["TypeScript", "Testing Libraries", "Build Tools"] }
      ]
    },
    "Backend Developer": {
      duration: "7-9 months",
      description: "Create server-side logic, databases, and APIs that power applications",
      skills: ["Server Languages", "Databases", "APIs", "Cloud Services", "Security"],
      steps: [
        { title: "Choose Backend Language", duration: "2-3 weeks", resources: ["Python/Node.js Basics", "Language Documentation"] },
        { title: "Database Fundamentals", duration: "4-5 weeks", resources: ["SQL Tutorial", "MongoDB University", "Database Design"] },
        { title: "Web Framework Mastery", duration: "8-10 weeks", resources: ["Django/Express Documentation", "Framework Tutorials"] },
        { title: "API Development", duration: "6-8 weeks", resources: ["REST API Design", "GraphQL", "API Documentation"] },
        { title: "Deployment & DevOps", duration: "6-8 weeks", resources: ["Docker", "AWS/Heroku", "CI/CD Pipelines"] }
      ]
    },
    "Full-Stack Developer": {
      duration: "10-12 months", 
      description: "Master both frontend and backend development for complete web applications",
      skills: ["Frontend Frameworks", "Backend APIs", "Databases", "Version Control", "Deployment"],
      steps: [
        { title: "Frontend Foundation", duration: "6-8 weeks", resources: ["HTML/CSS/JS Basics", "React or Vue"] },
        { title: "Backend Development", duration: "8-10 weeks", resources: ["Node.js/Python", "Express/Django", "Database Integration"] },
        { title: "Full-Stack Projects", duration: "8-10 weeks", resources: ["MERN/MEAN Stack", "Project-based Learning"] },
        { title: "DevOps & Deployment", duration: "4-6 weeks", resources: ["Docker", "Cloud Platforms", "CI/CD"] },
        { title: "Advanced Patterns", duration: "6-8 weeks", resources: ["Microservices", "Testing", "Performance Optimization"] }
      ]
    },
    "Data Scientist": {
      duration: "8-12 months",
      description: "Extract insights from data using statistical analysis and machine learning",
      skills: ["Python/R", "Statistics", "Machine Learning", "Data Visualization", "SQL"],
      steps: [
        { title: "Python & Statistics", duration: "6-8 weeks", resources: ["Python for Data Analysis", "Statistics Course"] },
        { title: "Data Manipulation", duration: "4-6 weeks", resources: ["Pandas", "NumPy", "SQL Fundamentals"] },
        { title: "Machine Learning", duration: "10-12 weeks", resources: ["Scikit-learn", "Andrew Ng Course", "Kaggle Learn"] },
        { title: "Data Visualization", duration: "3-4 weeks", resources: ["Matplotlib", "Seaborn", "Plotly"] },
        { title: "Projects & Portfolio", duration: "8-10 weeks", resources: ["Kaggle Competitions", "Personal Projects"] }
      ]
    },
    "Mobile Developer": {
      duration: "6-9 months",
      description: "Build native and cross-platform mobile applications",
      skills: ["Mobile Frameworks", "UI/UX Design", "APIs", "App Store Deployment", "Performance"],
      steps: [
        { title: "Choose Platform", duration: "1-2 weeks", resources: ["iOS vs Android vs Cross-platform"] },
        { title: "Framework Learning", duration: "8-10 weeks", resources: ["React Native", "Flutter", "Swift/Kotlin"] },
        { title: "UI/UX for Mobile", duration: "4-6 weeks", resources: ["Mobile Design Principles", "Navigation Patterns"] },
        { title: "API Integration", duration: "4-6 weeks", resources: ["REST APIs", "State Management", "Offline Storage"] },
        { title: "Publishing & Optimization", duration: "3-4 weeks", resources: ["App Store Guidelines", "Performance Testing"] }
      ]
    },
    "DevOps Engineer": {
      duration: "8-10 months",
      description: "Bridge development and operations through automation and infrastructure",
      skills: ["Linux/Cloud", "Containerization", "CI/CD", "Monitoring", "Infrastructure as Code"],
      steps: [
        { title: "Linux & Cloud Basics", duration: "4-6 weeks", resources: ["Linux Command Line", "AWS/Azure Fundamentals"] },
        { title: "Containerization", duration: "6-8 weeks", resources: ["Docker", "Kubernetes", "Container Orchestration"] },
        { title: "CI/CD Pipelines", duration: "6-8 weeks", resources: ["Jenkins", "GitHub Actions", "GitLab CI"] },
        { title: "Infrastructure as Code", duration: "6-8 weeks", resources: ["Terraform", "Ansible", "CloudFormation"] },
        { title: "Monitoring & Security", duration: "4-6 weeks", resources: ["Prometheus", "Grafana", "Security Best Practices"] }
      ]
    }
  };

  // Popular Free Learning Platforms
  const platforms = [
    { name: "freeCodeCamp", url: "https://www.freecodecamp.org", desc: "Complete programming curriculum", color: "bg-green-100 text-green-700" },
    { name: "Coursera", url: "https://www.coursera.org", desc: "University courses free audit", color: "bg-blue-100 text-blue-700" },
    { name: "edX", url: "https://www.edx.org", desc: "Harvard, MIT courses", color: "bg-purple-100 text-purple-700" },
    { name: "Codecademy", url: "https://www.codecademy.com", desc: "Interactive coding lessons", color: "bg-yellow-100 text-yellow-700" },
    { name: "Khan Academy", url: "https://www.khanacademy.org", desc: "Programming basics", color: "bg-teal-100 text-teal-700" },
    { name: "MDN Web Docs", url: "https://developer.mozilla.org", desc: "Web development resources", color: "bg-orange-100 text-orange-700" },
    { name: "The Odin Project", url: "https://www.theodinproject.com", desc: "Full-stack curriculum", color: "bg-red-100 text-red-700" },
    { name: "Scrimba", url: "https://scrimba.com", desc: "Interactive video tutorials", color: "bg-pink-100 text-pink-700" },
    { name: "LeetCode", url: "https://leetcode.com", desc: "Coding interview practice", color: "bg-indigo-100 text-indigo-700" },
    { name: "Kaggle Learn", url: "https://www.kaggle.com/learn", desc: "Data science courses", color: "bg-cyan-100 text-cyan-700" },
    { name: "GitHub", url: "https://github.com", desc: "Open source learning", color: "bg-gray-100 text-gray-700" },
    { name: "Stack Overflow", url: "https://stackoverflow.com", desc: "Programming Q&A", color: "bg-orange-100 text-orange-600" }
  ];

  const categories = ['All', 'JavaScript', 'Python', 'Web Development', 'Frontend', 'Backend', 'Data Science', 'Algorithms', 'Mobile', 'System Design', 'DevOps', 'General'];

  const getTypeIcon = (type) => {
    switch(type) {
      case 'pdf': return <FileText className="w-5 h-5 text-red-500" />;
      case 'video': return <Video className="w-5 h-5 text-blue-500" />;
      case 'link': return <ExternalLink className="w-5 h-5 text-green-500" />;
      default: return <Code className="w-5 h-5 text-gray-500" />;
    }
  };

  // Fixed: Using useMemo for performance optimization
  const filteredResources = useMemo(() => {
    return resources.filter(resource => {
      const matchesSearch = resource.title.toLowerCase().includes(searchTerm.toLowerCase()) ||
                           resource.description.toLowerCase().includes(searchTerm.toLowerCase()) ||
                           resource.author.toLowerCase().includes(searchTerm.toLowerCase());
      const matchesCategory = selectedCategory === 'All' || resource.category === selectedCategory;
      return matchesSearch && matchesCategory;
    });
  }, [resources, searchTerm, selectedCategory]);

  // Fixed: Better validation with user feedback
  const validateForm = () => {
    const newErrors = {};
    if (!newResource.title.trim()) newErrors.title = "Title is required";
    if (!newResource.url.trim()) newErrors.url = "URL is required";
    if (!newResource.description.trim()) newErrors.description = "Description is required";
    if (!newResource.author.trim()) newErrors.author = "Author is required";
    
    // Basic URL validation
    try {
      new URL(newResource.url);
    } catch {
      if (newResource.url.trim()) newErrors.url = "Please enter a valid URL";
    }
    
    setErrors(newErrors);
    return Object.keys(newErrors).length === 0;
  };

  const handleAddResource = () => {
    if (validateForm()) {
      // Fixed: Better ID generation to avoid conflicts
      const newId = Math.max(...resources.map(r => r.id), 0) + 1;
      const resource = {
        ...newResource,
        id: newId,
        rating: 0,
        downloads: 0,
        title: newResource.title.trim(),
        url: newResource.url.trim(),
        description: newResource.description.trim(),
        author: newResource.author.trim()
      };
      setResources([...resources, resource]);
      setNewResource({
        title: '', type: 'link', category: 'JavaScript', language: 'JavaScript', url: '', description: '', author: ''
      });
      setErrors({});
      setShowAddForm(false);
    }
  };

  // Fixed: Memoized category stats calculation
  const categoryStats = useMemo(() => {
    const stats = {};
    categories.slice(1).forEach(cat => {
      stats[cat] = resources.filter(r => r.category === cat).length;
    });
    return stats;
  }, [resources, categories]);

  // Helper component for text truncation (replaces line-clamp classes)
  const TruncatedText = ({ text, lines = 2, className = "" }) => {
    return (
      <div 
        className={`overflow-hidden ${className}`}
        style={{
          display: '-webkit-box',
          WebkitLineClamp: lines,
          WebkitBoxOrient: 'vertical'
        }}
      >
        {text}
      </div>
    );
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-blue-50 via-indigo-50 to-purple-50 p-4">
      <div className="max-w-7xl mx-auto">
        {/* Header */}
        <div className="text-center mb-8">
          <h1 className="text-5xl font-bold text-gray-800 mb-3 flex items-center justify-center gap-3">
            <Code className="w-12 h-12 text-indigo-600" />
            Programming Resource Hub
          </h1>
          <p className="text-xl text-gray-600 mb-4">Your complete gateway to free programming education & career paths</p>
          <div className="flex justify-center items-center gap-6 text-sm text-gray-500">
            <span className="flex items-center gap-2 bg-white px-4 py-2 rounded-full shadow">
              <Users className="w-4 h-4" />
              25,847 contributors
            </span>
            <span className="flex items-center gap-2 bg-white px-4 py-2 rounded-full shadow">
              <Download className="w-4 h-4" />
              8,563,200 downloads
            </span>
            <span className="flex items-center gap-2 bg-white px-4 py-2 rounded-full shadow">
              <BookOpen className="w-4 h-4" />
              {resources.length} resources
            </span>
          </div>
        </div>

        {/* Fixed: Improved tab navigation with ARIA attributes */}
        <div className="flex justify-center mb-8">
          <div className="bg-white rounded-2xl shadow-lg p-2 flex" role="tablist">
            <button
              onClick={() => setActiveTab('resources')}
              className={`px-6 py-3 rounded-xl font-semibold transition-all flex items-center gap-2 ${
                activeTab === 'resources' 
                  ? 'bg-indigo-600 text-white shadow-md' 
                  : 'text-gray-600 hover:text-gray-800 hover:bg-gray-50'
              }`}
              role="tab"
              aria-selected={activeTab === 'resources'}
              aria-label="Browse programming resources"
            >
              <BookOpen className="w-5 h-5" />
              Browse Resources
            </button>
            <button
              onClick={() => setActiveTab('paths')}
              className={`px-6 py-3 rounded-xl font-semibold transition-all flex items-center gap-2 ${
                activeTab === 'paths' 
                  ? 'bg-indigo-600 text-white shadow-md' 
                  : 'text-gray-600 hover:text-gray-800 hover:bg-gray-50'
              }`}
              role="tab"
              aria-selected={activeTab === 'paths'}
              aria-label="View career learning paths"
            >
              <Map className="w-5 h-5" />
              Career Paths
            </button>
            <button
              onClick={() => setActiveTab('essential')}
              className={`px-6 py-3 rounded-xl font-semibold transition-all flex items-center gap-2 ${
                activeTab === 'essential' 
                  ? 'bg-indigo-600 text-white shadow-md' 
                  : 'text-gray-600 hover:text-gray-800 hover:bg-gray-50'
              }`}
              role="tab"
              aria-selected={activeTab === 'essential'}
              aria-label="View essential student sites"
            >
              <Star className="w-5 h-5" />
              Essential Sites
            </button>
          </div>
        </div>

        {activeTab === 'essential' && (
          <div>
            {/* Essential Sites Introduction */}
            <div className="bg-gradient-to-r from-yellow-400 via-orange-400 to-red-400 rounded-2xl shadow-lg p-8 mb-8 text-center text-white">
              <h2 className="text-4xl font-bold mb-4 flex items-center justify-center gap-3">
                <Star className="w-10 h-10" />
                Essential Student Sites
              </h2>
              <p className="text-xl mb-6 text-yellow-100">
                24 must-know websites every programming student should bookmark
              </p>
              <div className="grid grid-cols-2 md:grid-cols-4 gap-4 text-sm">
                <div className="flex items-center justify-center gap-2 bg-white/20 px-4 py-2 rounded-full">
                  <Target className="w-4 h-4" />
                  Critical Tools
                </div>
                <div className="flex items-center justify-center gap-2 bg-white/20 px-4 py-2 rounded-full">
                  <BookOpen className="w-4 h-4" />
                  Learning Platforms
                </div>
                <div className="flex items-center justify-center gap-2 bg-white/20 px-4 py-2 rounded-full">
                  <Users className="w-4 h-4" />
                  Communities
                </div>
                <div className="flex items-center justify-center gap-2 bg-white/20 px-4 py-2 rounded-full">
                  <Code className="w-4 h-4" />
                  Development Tools
                </div>
              </div>
            </div>

            {/* Priority Legend */}
            <div className="bg-white rounded-2xl shadow-lg p-6 mb-8">
              <h3 className="text-xl font-semibold mb-4 text-center">Priority Levels</h3>
              <div className="flex justify-center gap-6 text-sm">
                <div className="flex items-center gap-2">
                  <div className="w-4 h-4 bg-red-500 rounded-full"></div>
                  <span className="font-medium">Critical - Must Have</span>
                </div>
                <div className="flex items-center gap-2">
                  <div className="w-4 h-4 bg-orange-400 rounded-full"></div>
                  <span className="font-medium">High - Very Important</span>
                </div>
                <div className="flex items-center gap-2">
                  <div className="w-4 h-4 bg-yellow-400 rounded-full"></div>
                  <span className="font-medium">Medium - Helpful</span>
                </div>
              </div>
            </div>

            {/* Essential Sites Grid */}
            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
              {essentialSites.map((site, index) => {
                const getPriorityColor = (priority) => {
                  switch(priority) {
                    case 'Critical': return 'bg-red-500';
                    case 'High': return 'bg-orange-400';
                    case 'Medium': return 'bg-yellow-400';
                    default: return 'bg-gray-400';
                  }
                };

                const getPriorityBorder = (priority) => {
                  switch(priority) {
                    case 'Critical': return 'border-red-200 hover:border-red-300';
                    case 'High': return 'border-orange-200 hover:border-orange-300';
                    case 'Medium': return 'border-yellow-200 hover:border-yellow-300';
                    default: return 'border-gray-200 hover:border-gray-300';
                  }
                };

                return (
                  <div 
                    key={index} 
                    className={`bg-white rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300 p-6 border-2 ${getPriorityBorder(site.priority)} group cursor-pointer`}
                    onClick={() => window.open(site.url, '_blank', 'noopener,noreferrer')}
                  >
                    <div className="flex items-start justify-between mb-4">
                      <div className="flex items-center gap-3">
                        <div className={`w-3 h-3 rounded-full ${getPriorityColor(site.priority)}`}></div>
                        <span className="text-xs bg-gray-100 text-gray-700 px-3 py-1 rounded-full font-medium">
                          {site.category}
                        </span>
                      </div>
                      <span className={`text-xs px-3 py-1 rounded-full font-medium ${
                        site.priority === 'Critical' ? 'bg-red-100 text-red-700' :
                        site.priority === 'High' ? 'bg-orange-100 text-orange-700' :
                        'bg-yellow-100 text-yellow-700'
                      }`}>
                        {site.priority}
                      </span>
                    </div>
                    
                    <h3 className="font-bold text-xl text-gray-800 mb-3 group-hover:text-indigo-600 transition-colors">
                      {site.name}
                    </h3>
                    
                    <p className="text-gray-600 text-sm mb-6 leading-relaxed">
                      {site.description}
                    </p>
                    
                    <div className="flex items-center justify-between">
                      <span className="text-xs text-gray-500 font-mono bg-gray-50 px-3 py-1 rounded">
                        {site.url.replace('https://', '')}
                      </span>
                      <div className="opacity-0 group-hover:opacity-100 transition-opacity">
                        <ExternalLink className="w-4 h-4 text-indigo-600" />
                      </div>
                    </div>
                  </div>
                );
              })}
            </div>

            {/* Quick Access Categories */}
            <div className="mt-12 bg-white rounded-2xl shadow-lg p-8">
              <h3 className="text-2xl font-bold text-gray-800 mb-6 text-center">Quick Access by Category</h3>
              <div className="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4">
                {['Development Tools', 'Learning', 'Community', 'Documentation', 'Practice', 'Interview Prep', 'Utilities', 'Design', 'Hosting', 'DevOps'].map((category) => {
                  const categoryCount = essentialSites.filter(site => site.category === category).length;
                  if (categoryCount === 0) return null;
                  
                  return (
                    <div key={category} className="text-center p-4 bg-gradient-to-b from-indigo-50 to-purple-50 rounded-xl border-2 border-indigo-100 hover:border-indigo-300 transition-all">
                      <div className="font-semibold text-indigo-700 text-sm mb-1">{category}</div>
                      <div className="text-xs text-indigo-500">{categoryCount} sites</div>
                    </div>
                  );
                })}
              </div>
            </div>

            {/* Student Tips */}
            <div className="mt-8 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-2xl shadow-lg p-8 text-white">
              <h3 className="text-2xl font-bold mb-6 text-center">💡 Pro Student Tips</h3>
              <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div className="bg-white/10 rounded-xl p-4">
                  <h4 className="font-semibold mb-3 flex items-center gap-2">
                    <CheckCircle className="w-5 h-5" />
                    Daily Essentials
                  </h4>
                  <ul className="text-sm space-y-2 text-indigo-100">
                    <li>• Start every project with GitHub repo</li>
                    <li>• Use VS Code with essential extensions</li>
                    <li>• Keep Stack Overflow bookmarked</li>
                    <li>• Practice on LeetCode daily</li>
                  </ul>
                </div>
                <div className="bg-white/10 rounded-xl p-4">
                  <h4 className="font-semibold mb-3 flex items-center gap-2">
                    <Target className="w-5 h-5" />
                    Learning Strategy
                  </h4>
                  <ul className="text-sm space-y-2 text-indigo-100">
                    <li>• Use MDN for web development reference</li>
                    <li>• Take free Coursera/edX courses</li>
                    <li>• Build projects and host on Netlify</li>
                    <li>• Join programming communities</li>
                  </ul>
                </div>
                <div className="bg-white/10 rounded-xl p-4">
                  <h4 className="font-semibold mb-3 flex items-center gap-2">
                    <Trophy className="w-5 h-5" />
                    Career Prep
                  </h4>
                  <ul className="text-sm space-y-2 text-indigo-100">
                    <li>• Build a strong GitHub portfolio</li>
                    <li>• Master Git version control</li>
                    <li>• Practice coding interviews</li>
                    <li>• Learn deployment platforms</li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        )}

        {activeTab === 'paths' && (
          <div>
            {/* Career Paths Introduction */}
            <div className="bg-white rounded-2xl shadow-lg p-8 mb-8 text-center">
              <h2 className="text-3xl font-bold text-gray-800 mb-4 flex items-center justify-center gap-3">
                <Target className="w-8 h-8 text-indigo-600" />
                Choose Your Programming Career Path
              </h2>
              <p className="text-lg text-gray-600 mb-6">Structured learning roadmaps to guide you from beginner to job-ready developer</p>
              <div className="grid grid-cols-2 md:grid-cols-4 gap-4 text-sm text-gray-500">
                <div className="flex items-center justify-center gap-2 bg-indigo-50 px-4 py-2 rounded-full">
                  <Calendar className="w-4 h-4" />
                  Structured Timeline
                </div>
                <div className="flex items-center justify-center gap-2 bg-green-50 px-4 py-2 rounded-full">
                  <CheckCircle className="w-4 h-4" />
                  Skill Progression
                </div>
                <div className="flex items-center justify-center gap-2 bg-blue-50 px-4 py-2 rounded-full">
                  <Trophy className="w-4 h-4" />
                  Job-Ready Skills
                </div>
                <div className="flex items-center justify-center gap-2 bg-purple-50 px-4 py-2 rounded-full">
                  <BookOpen className="w-4 h-4" />
                  Curated Resources
                </div>
              </div>
            </div>

            {/* Learning Paths Grid */}
            <div className="grid grid-cols-1 lg:grid-cols-2 gap-8">
              {Object.entries(learningPaths).map(([career, path]) => (
                <div key={career} className="bg-white rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300 overflow-hidden">
                  <div className="bg-gradient-to-r from-indigo-600 to-purple-600 p-6 text-white">
                    <h3 className="text-2xl font-bold mb-2">{career}</h3>
                    <p className="text-indigo-100 mb-4">{path.description}</p>
                    <div className="flex items-center gap-4 text-sm">
                      <div className="flex items-center gap-2">
                        <Calendar className="w-4 h-4" />
                        {path.duration}
                      </div>
                      <div className="flex items-center gap-2">
                        <Target className="w-4 h-4" />
                        {path.steps.length} Steps
                      </div>
                    </div>
                  </div>
                  
                  <div className="p-6">
                    {/* Skills Overview */}
                    <div className="mb-6">
                      <h4 className="font-semibold text-gray-700 mb-3">Key Skills You'll Learn:</h4>
                      <div className="flex flex-wrap gap-2">
                        {path.skills.map((skill, index) => (
                          <span key={index} className="bg-indigo-100 text-indigo-700 px-3 py-1 rounded-full text-sm font-medium">
                            {skill}
                          </span>
                        ))}
                      </div>
                    </div>
                    
                    {/* Learning Steps */}
                    <div>
                      <h4 className="font-semibold text-gray-700 mb-3">Learning Roadmap:</h4>
                      <div className="space-y-3">
                        {path.steps.map((step, index) => (
                          <div key={index} className="flex items-start gap-3 p-3 bg-gray-50 rounded-lg">
                            <div className="bg-indigo-600 text-white rounded-full w-6 h-6 flex items-center justify-center text-sm font-bold flex-shrink-0 mt-1">
                              {index + 1}
                            </div>
                            <div className="flex-1">
                              <div className="flex items-center justify-between mb-1">
                                <h5 className="font-medium text-gray-800">{step.title}</h5>
                                <span className="text-xs text-gray-500 bg-white px-2 py-1 rounded">{step.duration}</span>
                              </div>
                              <div className="text-xs text-gray-600">
                                Resources: {step.resources.join(', ')}
                              </div>
                            </div>
                          </div>
                        ))}
                      </div>
                    </div>
                  </div>
                </div>
              ))}
            </div>
          </div>
        )}

        {activeTab === 'resources' && (
          <div>
            {/* Popular Learning Platforms */}
            <div className="bg-white rounded-2xl shadow-lg p-6 mb-8">
              <h2 className="text-2xl font-bold text-gray-800 mb-6 flex items-center gap-2">
                <Star className="w-6 h-6 text-yellow-500" />
                Popular Free Learning Platforms
              </h2>
              <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-3">
                {platforms.map((platform, index) => (
                  <a
                    key={index}
                    href={platform.url}
                    target="_blank"
                    rel="noopener noreferrer"
                    className={`group p-4 rounded-xl border-2 hover:shadow-md transition-all text-center ${platform.color} border-transparent hover:border-gray-200`}
                    title={platform.desc}
                  >
                    <div className="font-semibold text-sm mb-1">
                      {platform.name}
                    </div>
                    <div className="text-xs opacity-75">
                      {platform.desc}
                    </div>
                  </a>
                ))}
              </div>
            </div>

            {/* Category Overview */}
            <div className="bg-white rounded-2xl shadow-lg p-6 mb-8">
              <h2 className="text-2xl font-bold text-gray-800 mb-6">Browse by Category</h2>
              <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
                {categories.slice(1).map((category) => (
                  <button
                    key={category}
                    onClick={() => setSelectedCategory(category)}
                    className={`p-4 rounded-xl border-2 transition-all ${
                      selectedCategory === category
                        ? 'border-indigo-500 bg-indigo-50 text-indigo-700'
                        : 'border-gray-200 hover:border-gray-300 text-gray-700 hover:bg-gray-50'
                    }`}
                    aria-label={`Filter by ${category} category`}
                  >
                    <div className="font-semibold">{category}</div>
                    <div className="text-sm text-gray-500">{categoryStats[category] || 0} resources</div>
                  </button>
                ))}
              </div>
            </div>

            {/* Search and Filters */}
            <div className="bg-white rounded-2xl shadow-lg p-6 mb-6">
              <div className="flex flex-col lg:flex-row gap-4 items-center">
                <div className="relative flex-1">
                  <Search className="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400 w-5 h-5" />
                  <input
                    type="text"
                    placeholder="Search resources, authors, or descriptions..."
                    className="w-full pl-12 pr-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-indigo-500 focus:border-transparent text-lg"
                    value={searchTerm}
                    onChange={(e) => setSearchTerm(e.target.value)}
                    aria-label="Search programming resources"
                  />
                </div>
                
                <div className="flex gap-3">
                  <select
                    className="px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-indigo-500 text-lg"
                    value={selectedCategory}
                    onChange={(e) => setSelectedCategory(e.target.value)}
                    aria-label="Filter by category"
                  >
                    {categories.map(cat => (
                      <option key={cat} value={cat}>{cat}</option>
                    ))}
                  </select>

                  <button
                    onClick={() => setShowAddForm(!showAddForm)}
                    className="bg-indigo-600 text-white px-6 py-3 rounded-xl hover:bg-indigo-700 transition-colors flex items-center gap-2 text-lg font-medium"
                    aria-label="Add new programming resource"
                  >
                    <Plus className="w-5 h-5" />
                    Add Resource
                  </button>
                </div>
              </div>
            </div>

            {/* Fixed: Enhanced Add Resource Form with validation */}
            {showAddForm && (
              <div className="bg-white rounded-2xl shadow-lg p-6 mb-6">
                <h3 className="text-xl font-semibold mb-6">Share a New Programming Resource</h3>
                <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                  <div>
                    <input
                      type="text"
                      placeholder="Resource Title"
                      className={`w-full px-4 py-3 border rounded-xl focus:ring-2 focus:ring-indigo-500 ${
                        errors.title ? 'border-red-300 bg-red-50' : 'border-gray-300'
                      }`}
                      value={newResource.title}
                      onChange={(e) => setNewResource({...newResource, title: e.target.value})}
                      required
                    />
                    {errors.title && <p className="text-red-600 text-sm mt-1">{errors.title}</p>}
                  </div>
                  
                  <div>
                    <input
                      type="url"
                      placeholder="Resource URL"
                      className={`w-full px-4 py-3 border rounded-xl focus:ring-2 focus:ring-indigo-500 ${
                        errors.url ? 'border-red-300 bg-red-50' : 'border-gray-300'
                      }`}
                      value={newResource.url}
                      onChange={(e) => setNewResource({...newResource, url: e.target.value})}
                      required
                    />
                    {errors.url && <p className="text-red-600 text-sm mt-1">{errors.url}</p>}
                  </div>
                  
                  <select
                    className="px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-indigo-500"
                    value={newResource.type}
                    onChange={(e) => setNewResource({...newResource, type: e.target.value})}
                    aria-label="Select resource type"
                  >
                    <option value="link">Website/Link</option>
                    <option value="video">Video/YouTube</option>
                    <option value="pdf">PDF/Book</option>
                  </select>
                  
                  <select
                    className="px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-indigo-500"
                    value={newResource.category}
                    onChange={(e) => setNewResource({...newResource, category: e.target.value})}
                    aria-label="Select resource category"
                  >
                    {categories.slice(1).map(cat => (
                      <option key={cat} value={cat}>{cat}</option>
                    ))}
                  </select>
                  
                  <div>
                    <input
                      type="text"
                      placeholder="Author/Creator Name"
                      className={`w-full px-4 py-3 border rounded-xl focus:ring-2 focus:ring-indigo-500 ${
                        errors.author ? 'border-red-300 bg-red-50' : 'border-gray-300'
                      }`}
                      value={newResource.author}
                      onChange={(e) => setNewResource({...newResource, author: e.target.value})}
                    />
                    {errors.author && <p className="text-red-600 text-sm mt-1">{errors.author}</p>}
                  </div>
                  
                  <input
                    type="text"
                    placeholder="Programming Language"
                    className="px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-indigo-500"
                    value={newResource.language}
                    onChange={(e) => setNewResource({...newResource, language: e.target.value})}
                  />
                  
                  <div className="md:col-span-2">
                    <textarea
                      placeholder="Description of the resource"
                      className={`w-full px-4 py-3 border rounded-xl focus:ring-2 focus:ring-indigo-500 resize-none ${
                        errors.description ? 'border-red-300 bg-red-50' : 'border-gray-300'
                      }`}
                      rows="3"
                      value={newResource.description}
                      onChange={(e) => setNewResource({...newResource, description: e.target.value})}
                    />
                    {errors.description && <p className="text-red-600 text-sm mt-1">{errors.description}</p>}
                  </div>
                  
                  <div className="md:col-span-2 flex gap-3">
                    <button
                      onClick={handleAddResource}
                      className="bg-indigo-600 text-white px-8 py-3 rounded-xl hover:bg-indigo-700 transition-colors font-medium"
                    >
                      Share Resource
                    </button>
                    <button
                      onClick={() => {
                        setShowAddForm(false);
                        setErrors({});
                      }}
                      className="bg-gray-300 text-gray-700 px-8 py-3 rounded-xl hover:bg-gray-400 transition-colors font-medium"
                    >
                      Cancel
                    </button>
                  </div>
                </div>
              </div>
            )}

            {/* Resources Grid */}
            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
              {filteredResources.map(resource => (
                <div key={resource.id} className="bg-white rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300 p-6 border border-gray-100">
                  <div className="flex items-start justify-between mb-4">
                    <div className="flex items-center gap-3">
                      {getTypeIcon(resource.type)}
                      <span className="text-xs bg-gray-100 text-gray-700 px-3 py-1 rounded-full font-medium">
                        {resource.type.toUpperCase()}
                      </span>
                    </div>
                    <div className="flex items-center gap-1 text-sm text-yellow-600">
                      <Star className="w-4 h-4 fill-current" />
                      {resource.rating}
                    </div>
                  </div>
                  
                  <TruncatedText 
                    text={resource.title}
                    lines={2}
                    className="font-bold text-lg text-gray-800 mb-3 leading-tight"
                  />
                  
                  <div className="flex flex-wrap gap-2 mb-4">
                    <span className="text-xs bg-indigo-100 text-indigo-700 px-3 py-1 rounded-full font-medium">
                      {resource.category}
                    </span>
                    <span className="text-xs bg-green-100 text-green-700 px-3 py-1 rounded-full font-medium">
                      {resource.language}
                    </span>
                  </div>
                  
                  <TruncatedText 
                    text={resource.description}
                    lines={3}
                    className="text-gray-600 text-sm mb-4"
                  />
                  
                  <div className="flex items-center justify-between text-sm text-gray-500 mb-6">
                    <span className="font-medium">By {resource.author}</span>
                    <span className="flex items-center gap-1">
                      <Download className="w-3 h-3" />
                      {resource.downloads.toLocaleString()}
                    </span>
                  </div>
                  
                  <a
                    href={resource.url}
                    target="_blank"
                    rel="noopener noreferrer"
                    className="w-full bg-gradient-to-r from-indigo-600 to-purple-600 text-white py-3 px-6 rounded-xl hover:from-indigo-700 hover:to-purple-700 transition-all flex items-center justify-center gap-2 font-medium"
                    aria-label={`Access ${resource.title} resource`}
                  >
                    <ExternalLink className="w-4 h-4" />
                    Access Resource
                  </a>
                </div>
              ))}
            </div>

            {filteredResources.length === 0 && (
              <div className="text-center py-16">
                <Code className="w-20 h-20 text-gray-300 mx-auto mb-6" />
                <h3 className="text-2xl font-semibold text-gray-500 mb-2">No resources found</h3>
                <p className="text-gray-400">Try adjusting your search terms or browse by category</p>
              </div>
            )}
          </div>
        )}
      </div>
    </div>
  );
};

export default ProgrammingResourceHub;
