# Project File Tree for TradeCraft.Lifestyle Simulations

This file tree organizes the development of React-based simulations for the *Elite Tradecraft Curriculum* within *TradeCraft.Lifestyle*, excluding `index.html` as the home start page and main site are managed in a separate file tree. The structure supports scalability, premium-tier access, and integration with Firebase and xAI API for the simulations (Elicitation, Dead Drops, Surveillance/Counter-Surveillance/SDRs, Brush Passes/Bumps, Flaps and Seals).

```
elite_tradecraft_simulations/
├── public/                           # Static assets and simulation entry points
│   ├── elicitation_simulation.html    # Elicitation simulation
│   ├── dead_drops_simulation.html     # Dead Drops simulation
│   ├── surveillance_counter_sdr_simulation.html # Surveillance/SDR simulation
│   ├── brush_passes_bumps_simulation.html # Brush Passes/Bumps simulation
│   ├── flaps_seals_simulation.html    # Flaps and Seals simulation
│   ├── favicon.ico                   # App favicon
│   └── assets/                       # Images, fonts, etc.
│       ├── logo.png                  # TradeCraft.Lifestyle logo
│       └── icons/                    # Simulation-specific icons
│           ├── elicitation.svg
│           ├── dead_drop.svg
│           ├── surveillance.svg
│           ├── brush_pass.svg
│           └── flaps_seals.svg
├── src/                              # React source code
│   ├── components/                   # Reusable React components
│   │   ├── SimulationWrapper.jsx     # Wraps all simulations for consistent UI
│   │   ├── RoleSelector.jsx          # Role selection (PI, Parent, Enthusiast)
│   │   ├── ScenarioDisplay.jsx       # Displays scenario based on role
│   │   ├── FeedbackPanel.jsx         # Displays score and feedback
│   │   └── PremiumGate.jsx           # Restricts access to premium users
│   ├── simulations/                   # Simulation-specific logic
│   │   ├── ElicitationSim.jsx        # Elicitation simulation component
│   │   ├── DeadDropsSim.jsx          # Dead Drops simulation component
│   │   ├── SurveillanceSDRsSim.jsx   # Surveillance/SDR simulation component
│   │   ├── BrushPassesBumpsSim.jsx   # Brush Passes/Bumps simulation component
│   │   └── FlapsSealsSim.jsx         # Flaps and Seals simulation component
│   ├── utils/                        # Utility functions
│   │   ├── firebase.js               # Firebase initialization and auth
│   │   ├── xaiApi.js                 # xAI API integration
│   │   └── scoring.js                # Scoring logic for simulations
│   ├── styles/                       # Tailwind CSS and custom styles
│   │   ├── tailwind.css              # Tailwind configuration
│   │   └── simulation.css            # Custom styles
│   └── App.jsx                       # Main React app component for simulations
├── backend/                          # Node.js/Express backend
│   ├── src/
│   │   ├── routes/
│   │   │   ├── auth.js               # Authentication routes (login, premium check)
│   │   │   ├── simulations.js        # Simulation data routes
│   │   │   └── analytics.js          # xAI API analytics routes
│   │   ├── middleware/
│   │   │   ├── authMiddleware.js     # Verify premium-tier access
│   │   │   └── rateLimiter.js        # Prevent abuse of API calls
│   │   ├── services/
│   │   │   ├── firebaseService.js    # Firebase Firestore interactions
│   │   │   └── xaiService.js         # xAI API wrapper
│   │   └── server.js                 # Main Express server
│   ├── .env                          # Environment variables (API keys)
│   └── package.json                  # Backend dependencies
├── tests/                            # Unit and integration tests
│   ├── components/                   # Component tests
│   │   ├── SimulationWrapper.test.js
│   │   └── FeedbackPanel.test.js
│   ├── simulations/                  # Simulation tests
│   │   ├── ElicitationSim.test.js
│   │   └── SurveillanceSDRsSim.test.js
│   └── backend/                      # Backend tests
│       ├── auth.test.js              # Auth route tests
│       └── simulations.test.js       # Simulation data tests
├── docs/                             # Documentation
│   ├── backend_guide.md              # Backend setup guide
│   ├── api_spec.md                   # API endpoints specification
│   └── deployment.md                 # Deployment instructions
├── scripts/                          # Build and deploy scripts
│   ├── build.sh                      # Build front-end
│   └── deploy.sh                     # Deploy to hosting
├── .gitignore                        # Git ignore file
├── package.json                      # Front-end dependencies
├── README.md                         # Project overview
└── tailwind.config.js                # Tailwind CSS configuration
```

## Notes
- **public/**: Contains simulation `.html` files (from previous artifacts) and static assets; `index.html` removed as per your instruction.
- **src/**: Houses React components, simulation logic, and utilities for Firebase/xAI API integration.
- **backend/**: Node.js/Express backend for authentication, data storage, and analytics.
- **tests/**: Jest tests for components and backend routes.
- **docs/**: Includes the updated backend guide (below) and API/deployment docs.
- **scripts/**: Automates build and deployment for scalability.