
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bioplasm NLS V6 Medical Database - Anavrin Wellness</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        .gradient-bg { background: linear-gradient(135deg, #1e40af 0%, #3730a3 50%, #581c87 100%); }
        .condition-card { transition: all 0.3s ease; cursor: pointer; }
        .condition-card:hover { transform: translateY(-2px); box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15); }
    </style>
</head>
<body class="bg-gray-50">
    <header class="gradient-bg text-white shadow-lg">
        <div class="container mx-auto px-6 py-4">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-4">
                    <div class="text-3xl">🔬</div>
                    <div>
                        <h1 class="text-2xl font-bold">Bioplasm NLS V6 Database</h1>
                        <p class="text-blue-100 text-sm">Anavrin Wellness - Complete Version Protocol Database</p>
                    </div>
                </div>
                <div class="text-right">
                    <div class="text-sm text-blue-100">Total Conditions</div>
                    <div class="text-xl font-bold" id="totalCount">Loading...</div>
                </div>
            </div>
        </div>

    <!-- Search Section -->
    <div class="bg-white shadow-sm border-b">
        <div class="container mx-auto px-6 py-4">
            <div class="flex flex-col lg:flex-row gap-4 items-center">
                <div class="flex-1 relative">
                    <input type="text" id="searchInput" placeholder="Search medical conditions..." 
                           class="w-full pl-12 pr-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                    <div class="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
                        </svg>
                    </div>
                </div>
                <select id="systemFilter" class="px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                    <option value="">All Categories (16 Total)</option>
                    <option value="cardiovascular">1. Cardiovascular System</option>
                    <option value="respiratory">2. Respiratory System</option>
                    <option value="digestive">3. Digestive System</option>
                    <option value="neurological">4. Neurology & CNS</option>
                    <option value="endocrine">5. Endocrine System</option>
                    <option value="renal">6. Renal & Urinary</option>
                    <option value="musculoskeletal">7. Musculoskeletal</option>
                    <option value="dermatology">8. Dermatology</option>
                    <option value="detoxification">9. Detoxification & Spike Proteins</option>
                    <option value="parasites">10. Parasites & Infections</option>
                    <option value="sports">11. Sports Medicine & Injury Recovery</option>
                    <option value="mental">12. Mental Health & Psychiatry</option>
                    <option value="womens">13. Women's Health & Gynecology</option>
                    <option value="mens">14. Men's Health & Urology</option>
                    <option value="pediatric">15. Pediatric & Child Health</option>
                    <option value="geriatric">16. Geriatric & Age-Related</option>
                </select>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto px-6 py-8">
        <div class="mb-6">
            <div class="text-gray-600">
                Showing <span id="resultCount" class="font-semibold text-blue-600">0</span> conditions across 16 medical categories
            </div>
        </div>

        <!-- Conditions Grid -->
        <div id="conditionsGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
            <!-- Conditions will be populated here -->
        </div>
    </main>

    <!-- Modal -->
    <div id="conditionModal" class="fixed inset-0 bg-black bg-opacity-50 hidden z-50">
        <div class="flex items-center justify-center min-h-screen p-4">
            <div class="bg-white rounded-2xl max-w-4xl w-full max-h-[90vh] overflow-y-auto">
                <div class="sticky top-0 bg-white border-b px-6 py-4 flex items-center justify-between">
                    <h2 id="modalTitle" class="text-2xl font-bold text-gray-800"></h2>
                    <button id="closeModal" class="text-gray-400 hover:text-gray-600 text-2xl">×</button>
                </div>
                <div class="p-6" id="modalContent"></div>
            </div>
        </div>
    </div>

    <script>
        // Complete Medical Conditions Database - Version 53 (All 16 Categories + Comprehensive Disease List)
        const medicalConditions = [
            // Category 1: Spike Protein & Detoxification Protocols
            {
                name: "Spike Protein Detox",
                category: "detoxification",
                systems: ["Immune System", "Cardiovascular System", "Respiratory System"],
                whatItIs: "Spike protein detoxification protocol addresses the presence of spike proteins from viral infections or vaccinations that may persist in the body. These proteins can cause ongoing inflammation, clotting issues, and immune dysfunction.",
                howItAffects: "Causes chronic fatigue, brain fog, cardiovascular issues, clotting disorders, and immune system dysfunction. Can lead to long-term inflammatory responses, autoimmune reactions, and vascular damage.",
                etalons: {
                    primaryOrgan: ["Spike protein structures", "ACE2 receptors", "Endothelial cells", "Immune cells", "Lymphatic system"],
                    pathomorphology: ["Protein aggregation", "Vascular inflammation", "Immune dysregulation", "Cellular damage"],
                    associatedSystems: ["Cardiovascular system", "Nervous system", "Respiratory system", "Detoxification pathways"],
                    biochemical: ["Spike proteins", "Inflammatory cytokines", "D-dimer", "Fibrinogen", "Oxidative stress markers", "Glutathione"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in spike protein etalons indicate chronic protein burden. Red triangles suggest acute inflammatory response. Black squares indicate severe cellular damage.",
                    graphNumbers: "Numbers 5-6 in spike protein etalons indicate high protein load. Numbers 4-5 in detoxification etalons suggest impaired clearance.",
                    anabolismCatabolism: "Red catabolism predominant in affected tissues. Blue anabolism compromised in cellular repair mechanisms.",
                    isoline: "Mild spike burden range 0.3-0.5, moderate burden 0.5-0.7, severe burden 0.7-0.9",
                    kccValues: "KCC < 0.4 for spike protein etalons indicates active protein presence. Healthy cellular etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate established protein-related damage",
                    biochemicalHomeostasis: "E values 1 or 7 in inflammatory and clotting etalons indicate significant dysfunction",
                    vegetativeTest: "+15% or more strengthening with spike protein neutralizing and detoxification preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete spike protein assessment with focus on protein distribution and inflammatory response patterns",
                    focusedAnalysis: "Detailed analysis of spike protein binding sites, vascular inflammation, and immune system activation",
                    metaTherapy: {
                        selection: "Select spike protein etalons with highest activity (lowest KCC values)",
                        settings: "Level 4-5, Therapy mode, 25-30 minutes per session",
                        sessions: "3 sessions per week initially, monitor symptoms and inflammatory markers",
                        focus: "Maximum 3-4 spike protein etalons per session to prevent detox overload"
                    },
                    vegetativeTest: "Test energetic compatibility with spike protein neutralizing, anti-inflammatory, and cellular repair preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily) or sugar pellets (4 pellets 4x daily). Duration: 6-8 weeks per cycle"
                },
                steps: [
                    "Comprehensive spike protein distribution scan",
                    "Analysis of protein binding and inflammatory response",
                    "Meta-therapy on spike protein neutralization etalons",
                    "Vegetative testing of detoxification support preparations",
                    "Cellular repair and recovery assessment"
                ],
                targets: ["Spike proteins", "ACE2 receptors", "Endothelial cells", "Immune cells"],
                notes: [
                    "CRITICAL: Support detoxification pathways with adequate hydration and nutrition",
                    "Monitor for Herxheimer reactions during initial treatment",
                    "Antioxidant support crucial during detoxification process",
                    "Consider cardiovascular monitoring if clotting issues present"
                ]
            },

            // Category 2: Parasites & Infections
            {
                name: "Intestinal Parasites",
                category: "parasites",
                systems: ["Digestive System", "Immune System"],
                whatItIs: "Intestinal parasites include protozoa (Giardia, Cryptosporidium, Entamoeba) and helminths (roundworms, tapeworms, hookworms) that infect the gastrointestinal tract and can cause chronic digestive and systemic symptoms.",
                howItAffects: "Causes abdominal pain, diarrhea, bloating, malabsorption, weight loss, and fatigue. Can lead to nutritional deficiencies, anemia, immune suppression, and chronic inflammatory conditions.",
                etalons: {
                    primaryOrgan: ["Small intestine", "Large intestine", "Intestinal wall", "Gut microbiome", "Immune cells"],
                    pathomorphology: ["Parasitic cysts", "Intestinal inflammation", "Mucosal damage", "Microbiome disruption"],
                    associatedSystems: ["Immune system", "Lymphatic system", "Nervous system", "Detoxification system"],
                    biochemical: ["Parasitic antigens", "Eosinophils", "IgE antibodies", "Inflammatory cytokines", "Digestive enzymes"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in parasitic etalons indicate chronic infestation. Red triangles suggest acute parasitic activity. Black squares indicate severe intestinal damage.",
                    graphNumbers: "Numbers 5-6 in parasitic organism etalons indicate active infestation. Numbers 4-5 in immune response etalons suggest ongoing battle.",
                    anabolismCatabolism: "Red catabolism in infected intestinal tissue. Blue anabolism disrupted by parasitic interference.",
                    isoline: "Mild infestation range 0.3-0.5, moderate infestation 0.5-0.7, severe infestation 0.7-0.9",
                    kccValues: "KCC < 0.4 for parasitic etalons indicates active infestation. Healthy intestinal etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established parasitic changes",
                    biochemicalHomeostasis: "E values 1 or 7 in immune and digestive etalons indicate significant parasitic burden",
                    vegetativeTest: "+15% or more strengthening with antiparasitic and immune support preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete gastrointestinal assessment with focus on parasitic organism detection and immune response",
                    focusedAnalysis: "Detailed analysis of parasitic species, infestation severity, and intestinal damage patterns",
                    metaTherapy: {
                        selection: "Select parasitic organism etalons with highest activity (lowest KCC values)",
                        settings: "Level 4-5, Therapy mode, 20-25 minutes per session",
                        sessions: "Daily sessions for 2 weeks, then 3x weekly, monitor stool and symptoms",
                        focus: "Maximum 3-4 parasitic etalons per session to prevent die-off overload"
                    },
                    vegetativeTest: "Test energetic compatibility with antiparasitic, digestive healing, and immune support preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily before meals) or sugar pellets (4 pellets 4x daily). Duration: 4-6 weeks per cycle"
                },
                steps: [
                    "Comprehensive parasitic organism scan",
                    "Analysis of infestation patterns and immune response",
                    "Meta-therapy on parasitic elimination etalons",
                    "Vegetative testing of antiparasitic preparations",
                    "Intestinal healing and microbiome restoration"
                ],
                targets: ["Parasitic organisms", "Intestinal wall", "Immune cells", "Gut microbiome"],
                notes: [
                    "CRITICAL: Monitor for die-off reactions (Herxheimer response)",
                    "Maintain strict hygiene to prevent reinfection",
                    "Support liver detoxification during parasite elimination",
                    "Consider family member testing and treatment if indicated"
                ]
            },

            // Category 3: Sports Medicine & Injury Recovery
            {
                name: "Acute Sports Injury",
                category: "sports",
                systems: ["Musculoskeletal System", "Vascular System"],
                whatItIs: "Acute sports injuries include sprains, strains, contusions, and fractures occurring during athletic activities. These injuries involve damage to muscles, ligaments, tendons, bones, or joints requiring immediate intervention.",
                howItAffects: "Causes pain, swelling, bruising, loss of function, and reduced athletic performance. Can lead to chronic pain, joint instability, reduced range of motion, and increased risk of re-injury if not properly treated.",
                etalons: {
                    primaryOrgan: ["Injured muscle fibers", "Ligaments", "Tendons", "Joint capsules", "Bone tissue"],
                    pathomorphology: ["Tissue inflammation", "Muscle fiber tears", "Ligament sprains", "Hematoma formation", "Scar tissue"],
                    associatedSystems: ["Circulatory system", "Lymphatic system", "Nervous system", "Immune system"],
                    biochemical: ["Inflammatory mediators", "Growth factors", "Collagen", "Creatine kinase", "Lactate dehydrogenase"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in injured tissue etalons indicate chronic damage. Red triangles suggest acute inflammatory response. Black squares indicate severe tissue destruction.",
                    graphNumbers: "Numbers 5-6 in tissue damage etalons indicate severe injury. Numbers 4-5 in inflammatory etalons suggest active healing response.",
                    anabolismCatabolism: "Red catabolism predominant in damaged tissue during acute phase. Blue anabolism increases during healing phase.",
                    isoline: "Mild injury range 0.3-0.5, moderate injury 0.5-0.7, severe injury 0.7-0.9",
                    kccValues: "KCC < 0.4 for tissue damage etalons indicates active injury. Healthy tissue etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate acute tissue changes",
                    biochemicalHomeostasis: "E values 1 or 7 in inflammatory marker etalons indicate significant tissue damage",
                    vegetativeTest: "+12% or more strengthening with tissue repair and anti-inflammatory preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete musculoskeletal assessment with focus on injury extent and tissue damage patterns",
                    focusedAnalysis: "Detailed analysis of tissue integrity, inflammatory response, and healing capacity",
                    metaTherapy: {
                        selection: "Select tissue damage etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 20-25 minutes per session",
                        sessions: "Daily sessions first week, then 3x weekly, monitor pain and function",
                        focus: "Maximum 3-4 injury-specific etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with tissue repair, anti-inflammatory, and circulation-enhancing preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily) or sugar pellets (4 pellets 4x daily). Duration: 4-8 weeks depending on injury severity"
                },
                steps: [
                    "Injury assessment and tissue damage evaluation",
                    "Analysis of inflammatory response and healing potential",
                    "Meta-therapy on tissue repair etalons",
                    "Vegetative testing of healing acceleration preparations",
                    "Recovery progress and function restoration evaluation"
                ],
                targets: ["Injured tissues", "Inflammatory cells", "Blood vessels", "Nerve endings"],
                notes: [
                    "CRITICAL: Apply RICE protocol (Rest, Ice, Compression, Elevation) immediately",
                    "Avoid weight-bearing or stress on injured area during acute phase",
                    "Gradual return to activity based on healing progress",
                    "Consider imaging studies for severe injuries"
                ]
            },
            {
                name: "Muscle Recovery & Performance",
                category: "sports",
                systems: ["Musculoskeletal System", "Metabolic System"],
                whatItIs: "Muscle recovery and performance optimization involves addressing exercise-induced muscle damage, metabolic fatigue, and enhancing athletic performance through improved muscle function and energy systems.",
                howItAffects: "Causes muscle soreness, fatigue, reduced power output, and decreased athletic performance. Can lead to overtraining syndrome, increased injury risk, and compromised immune function if recovery is inadequate.",
                etalons: {
                    primaryOrgan: ["Skeletal muscle fibers", "Mitochondria", "Neuromuscular junctions", "Energy systems", "Muscle glycogen stores"],
                    pathomorphology: ["Muscle microtrauma", "Metabolic acidosis", "Glycogen depletion", "Oxidative stress", "Protein breakdown"],
                    associatedSystems: ["Cardiovascular system", "Respiratory system", "Endocrine system", "Nervous system"],
                    biochemical: ["Creatine phosphate", "ATP", "Lactate", "Growth hormone", "Testosterone", "Cortisol", "Antioxidants"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in muscle fatigue etalons indicate chronic overtraining. Red triangles suggest acute exercise stress. Black squares indicate severe metabolic dysfunction.",
                    graphNumbers: "Numbers 4-5 in energy system etalons indicate depletion. Numbers 3-4 in recovery etalons suggest good adaptation potential.",
                    anabolismCatabolism: "Red catabolism during intense training phases. Blue anabolism enhanced during recovery and adaptation phases.",
                    isoline: "Normal recovery range 0.2-0.4, delayed recovery 0.4-0.6, overtraining 0.6-0.8",
                    kccValues: "KCC < 0.5 for fatigue etalons indicates need for recovery focus. Optimal performance etalons show KCC > 0.8",
                    entropyAnalysis: "E values 2-4 in pathomorphology etalons indicate normal exercise adaptations",
                    biochemicalHomeostasis: "E values 1 or 7 in energy system etalons indicate significant metabolic stress",
                    vegetativeTest: "+10% or more strengthening with performance and recovery preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete athletic performance assessment with focus on muscle function and energy systems",
                    focusedAnalysis: "Detailed analysis of muscle recovery status, energy system efficiency, and performance limiting factors",
                    metaTherapy: {
                        selection: "Select muscle fatigue and energy system etalons with highest stress (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 25-30 minutes per session",
                        sessions: "3-4 sessions per week during training, monitor performance metrics",
                        focus: "Maximum 4-5 performance-related etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with performance enhancement, recovery acceleration, and energy optimization preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink before/after training) or sugar pellets (4 pellets 3x daily). Duration: Ongoing during training cycles"
                },
                steps: [
                    "Athletic performance and recovery assessment",
                    "Analysis of muscle function and energy systems",
                    "Meta-therapy on performance optimization etalons",
                    "Vegetative testing of athletic enhancement preparations",
                    "Performance metrics and recovery evaluation"
                ],
                targets: ["Skeletal muscle", "Mitochondria", "Energy systems", "Neuromuscular function"],
                notes: [
                    "CRITICAL: Adequate sleep (7-9 hours) essential for recovery and performance",
                    "Proper nutrition timing crucial for glycogen replenishment",
                    "Hydration status significantly impacts performance",
                    "Progressive overload principles must be followed to prevent overtraining"
                ]
            },

            // Category 4: Mental Health & Psychiatry
            {
                name: "Depression",
                category: "mental",
                systems: ["Nervous System", "Endocrine System"],
                whatItIs: "Depression is a mood disorder characterized by persistent feelings of sadness, hopelessness, and loss of interest in activities. It involves complex interactions between neurotransmitters, hormones, and brain circuits.",
                howItAffects: "Causes persistent sadness, fatigue, sleep disturbances, appetite changes, and cognitive impairment. Can lead to social isolation, work disability, relationship problems, and increased suicide risk.",
                etalons: {
                    primaryOrgan: ["Prefrontal cortex", "Limbic system", "Hippocampus", "Hypothalamus", "Neurotransmitter pathways"],
                    pathomorphology: ["Neurotransmitter imbalance", "Neuroinflammation", "Hippocampal atrophy", "HPA axis dysfunction"],
                    associatedSystems: ["Endocrine system", "Immune system", "Autonomic nervous system", "Sleep regulation"],
                    biochemical: ["Serotonin", "Dopamine", "Norepinephrine", "GABA", "Cortisol", "BDNF", "Inflammatory cytokines"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in limbic system etalons indicate chronic emotional dysfunction. Red triangles suggest acute depressive episodes. Black squares indicate severe neurochemical imbalance.",
                    graphNumbers: "Numbers 4-6 in neurotransmitter etalons indicate imbalance. Numbers 5-6 in stress response etalons suggest HPA axis dysfunction.",
                    anabolismCatabolism: "Red catabolism in stress response systems. Blue anabolism reduced in neuroplasticity and repair mechanisms.",
                    isoline: "Mild depression range 0.3-0.5, moderate depression 0.5-0.7, severe depression 0.7-0.9",
                    kccValues: "KCC < 0.4 for mood regulation etalons indicates active depression. Healthy mood etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate established neurochemical changes",
                    biochemicalHomeostasis: "E values 1 or 7 in neurotransmitter etalons indicate significant imbalance",
                    vegetativeTest: "+12% or more strengthening with mood-stabilizing and neurotransmitter-balancing preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete neuropsychiatric assessment with focus on neurotransmitter balance and stress response patterns",
                    focusedAnalysis: "Detailed analysis of mood regulation circuits, HPA axis function, and neuroinflammatory markers",
                    metaTherapy: {
                        selection: "Select mood dysregulation etalons with highest activity (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 25-30 minutes per session",
                        sessions: "2-3 sessions per week, monitor mood symptoms and energy levels",
                        focus: "Maximum 3-4 neuropsychiatric etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with mood-stabilizing, neurotransmitter-balancing, and stress-reducing preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 8-12 weeks per cycle"
                },
                steps: [
                    "Neuropsychiatric assessment and mood evaluation",
                    "Analysis of neurotransmitter balance and stress response",
                    "Meta-therapy on mood regulation etalons",
                    "Vegetative testing of mood stabilization preparations",
                    "Mental health symptom improvement evaluation"
                ],
                targets: ["Neurotransmitter pathways", "Limbic system", "HPA axis", "Prefrontal cortex"],
                notes: [
                    "CRITICAL: Professional mental health support essential - never replace psychiatric care",
                    "Monitor for suicidal ideation - seek immediate help if present",
                    "Lifestyle factors (exercise, sleep, nutrition) crucial for recovery",
                    "Coordinate with psychiatrist/psychologist for comprehensive treatment"
                ]
            },
            {
                name: "Anxiety Disorders",
                category: "mental",
                systems: ["Nervous System", "Autonomic System"],
                whatItIs: "Anxiety disorders involve excessive fear, worry, and physiological arousal that interferes with daily functioning. Includes generalized anxiety, panic disorder, social anxiety, and specific phobias.",
                howItAffects: "Causes excessive worry, restlessness, muscle tension, rapid heartbeat, and avoidance behaviors. Can lead to panic attacks, social isolation, work impairment, and development of secondary depression.",
                etalons: {
                    primaryOrgan: ["Amygdala", "Prefrontal cortex", "Autonomic nervous system", "Adrenal glands", "GABA receptors"],
                    pathomorphology: ["Amygdala hyperactivity", "Autonomic dysregulation", "Neurotransmitter imbalance", "Stress response dysfunction"],
                    associatedSystems: ["Cardiovascular system", "Respiratory system", "Digestive system", "Endocrine system"],
                    biochemical: ["GABA", "Serotonin", "Norepinephrine", "Cortisol", "Adrenaline", "Glutamate"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in anxiety circuit etalons indicate chronic hypervigilance. Red triangles suggest acute anxiety episodes. Black squares indicate severe autonomic dysfunction.",
                    graphNumbers: "Numbers 5-6 in amygdala etalons indicate hyperactivity. Numbers 4-5 in autonomic etalons suggest dysregulation.",
                    anabolismCatabolism: "Red catabolism in stress response systems during anxiety episodes. Blue anabolism disrupted in calming mechanisms.",
                    isoline: "Mild anxiety range 0.3-0.5, moderate anxiety 0.5-0.7, severe anxiety 0.7-0.85",
                    kccValues: "KCC < 0.4 for anxiety response etalons indicates active anxiety disorder. Healthy calm etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established anxiety patterns",
                    biochemicalHomeostasis: "E values 1 or 7 in GABA and stress hormone etalons indicate significant imbalance",
                    vegetativeTest: "+12% or more strengthening with anxiolytic and autonomic-balancing preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete anxiety response assessment with focus on fear circuits and autonomic function",
                    focusedAnalysis: "Detailed analysis of amygdala reactivity, autonomic balance, and neurotransmitter function",
                    metaTherapy: {
                        selection: "Select anxiety response etalons with highest activity (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 20-25 minutes per session",
                        sessions: "2-3 sessions per week, monitor anxiety levels and panic frequency",
                        focus: "Maximum 3 anxiety-related etalons per session to prevent overstimulation"
                    },
                    vegetativeTest: "Test energetic compatibility with anxiolytic, autonomic-balancing, and stress-reducing preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink during anxiety episodes) or sugar pellets (3 pellets as needed). Duration: 6-10 weeks per cycle"
                },
                steps: [
                    "Anxiety response system assessment",
                    "Analysis of fear circuits and autonomic function",
                    "Meta-therapy on anxiety regulation etalons",
                    "Vegetative testing of calming preparations",
                    "Anxiety symptom reduction evaluation"
                ],
                targets: ["Amygdala", "GABA receptors", "Autonomic nervous system", "Adrenal glands"],
                notes: [
                    "CRITICAL: Breathing techniques and mindfulness practices highly beneficial",
                    "Avoid caffeine and stimulants during acute anxiety phases",
                    "Regular exercise excellent for anxiety management",
                    "Consider cognitive behavioral therapy alongside energetic treatment"
                ]
            },

            // Category 5: Women's Health & Gynecology
            {
                name: "Menstrual Irregularities",
                category: "womens",
                systems: ["Reproductive System", "Endocrine System"],
                whatItIs: "Menstrual irregularities include abnormal cycle length, flow, or timing caused by hormonal imbalances, stress, weight changes, or underlying conditions like PCOS or thyroid disorders.",
                howItAffects: "Causes unpredictable periods, heavy or light bleeding, cramping, and fertility issues. Can lead to anemia, emotional distress, relationship problems, and difficulty conceiving.",
                etalons: {
                    primaryOrgan: ["Ovaries", "Uterus", "Hypothalamus", "Pituitary gland", "Endometrium"],
                    pathomorphology: ["Hormonal imbalance", "Ovarian dysfunction", "Endometrial irregularities", "HPO axis disruption"],
                    associatedSystems: ["Endocrine system", "Nervous system", "Thyroid system", "Adrenal system"],
                    biochemical: ["Estrogen", "Progesterone", "FSH", "LH", "Thyroid hormones", "Insulin", "Androgens"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in ovarian etalons indicate chronic dysfunction. Red triangles suggest acute hormonal fluctuations. Black squares indicate severe reproductive imbalance.",
                    graphNumbers: "Numbers 4-5 in hormonal etalons indicate imbalance. Numbers 5-6 in ovarian etalons suggest dysfunction.",
                    anabolismCatabolism: "Red catabolism during menstrual phase. Blue anabolism disrupted in follicular development.",
                    isoline: "Mild irregularity range 0.3-0.5, moderate irregularity 0.5-0.7, severe dysfunction 0.7-0.85",
                    kccValues: "KCC < 0.4 for hormonal balance etalons indicates active irregularity. Healthy cycle etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established hormonal changes",
                    biochemicalHomeostasis: "E values 1 or 7 in reproductive hormone etalons indicate significant imbalance",
                    vegetativeTest: "+12% or more strengthening with hormone-balancing and cycle-regulating preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete reproductive system assessment with focus on hormonal balance and ovarian function",
                    focusedAnalysis: "Detailed analysis of menstrual cycle patterns, hormone production, and reproductive organ health",
                    metaTherapy: {
                        selection: "Select hormonal imbalance etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 20-25 minutes per session",
                        sessions: "2 sessions per week, track menstrual cycle changes",
                        focus: "Maximum 3-4 reproductive etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with hormone-balancing, cycle-regulating, and reproductive support preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 3-6 menstrual cycles"
                },
                steps: [
                    "Reproductive hormone assessment",
                    "Analysis of menstrual cycle patterns and ovarian function",
                    "Meta-therapy on hormonal balance etalons",
                    "Vegetative testing of cycle regulation preparations",
                    "Menstrual cycle normalization evaluation"
                ],
                targets: ["Ovaries", "Uterus", "Hypothalamus", "Pituitary gland"],
                notes: [
                    "CRITICAL: Track menstrual cycles carefully to monitor progress",
                    "Stress management crucial for hormonal balance",
                    "Maintain healthy weight for optimal reproductive function",
                    "Consider gynecological evaluation for persistent irregularities"
                ]
            },
            {
                name: "Menopause Symptoms",
                category: "womens",
                systems: ["Reproductive System", "Endocrine System"],
                whatItIs: "Menopause is the natural cessation of menstruation due to declining ovarian hormone production, typically occurring between ages 45-55. Perimenopause involves transitional symptoms before complete cessation.",
                howItAffects: "Causes hot flashes, night sweats, mood changes, sleep disturbances, and vaginal dryness. Can lead to osteoporosis, cardiovascular disease, cognitive changes, and reduced quality of life.",
                etalons: {
                    primaryOrgan: ["Ovaries", "Adrenal glands", "Hypothalamus", "Bone tissue", "Cardiovascular system"],
                    pathomorphology: ["Ovarian atrophy", "Hormonal decline", "Vasomotor instability", "Bone density loss"],
                    associatedSystems: ["Cardiovascular system", "Skeletal system", "Nervous system", "Urogenital system"],
                    biochemical: ["Estrogen", "Progesterone", "FSH", "LH", "Testosterone", "Bone markers", "Lipid profile"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in ovarian etalons indicate hormonal decline. Red triangles suggest acute vasomotor symptoms. Black squares indicate severe estrogen deficiency.",
                    graphNumbers: "Numbers 5-6 in estrogen etalons indicate deficiency. Numbers 4-5 in bone etalons suggest density loss.",
                    anabolismCatabolism: "Red catabolism in reproductive tissues. Blue anabolism reduced in bone formation and tissue repair.",
                    isoline: "Early menopause range 0.3-0.5, established menopause 0.5-0.7, severe symptoms 0.7-0.85",
                    kccValues: "KCC < 0.4 for estrogen deficiency etalons indicates active menopause. Healthy hormone etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate established menopausal changes",
                    biochemicalHomeostasis: "E values 1 or 7 in estrogen and bone marker etalons indicate significant deficiency",
                    vegetativeTest: "+12% or more strengthening with hormone replacement and bone support preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete menopausal assessment with focus on hormonal status and symptom severity",
                    focusedAnalysis: "Detailed analysis of estrogen deficiency, vasomotor symptoms, and bone health markers",
                    metaTherapy: {
                        selection: "Select menopausal symptom etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 25-30 minutes per session",
                        sessions: "2-3 sessions per week, monitor symptom frequency and intensity",
                        focus: "Maximum 3-4 menopausal etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with hormone-balancing, vasomotor-stabilizing, and bone-protective preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 8-12 weeks per cycle"
                },
                steps: [
                    "Menopausal status and symptom assessment",
                    "Analysis of hormonal decline and system effects",
                    "Meta-therapy on menopausal symptom etalons",
                    "Vegetative testing of hormone support preparations",
                    "Symptom relief and quality of life evaluation"
                ],
                targets: ["Ovaries", "Hypothalamus", "Bone tissue", "Cardiovascular system"],
                notes: [
                    "CRITICAL: Bone density monitoring essential for osteoporosis prevention",
                    "Cardiovascular risk assessment important during menopause",
                    "Lifestyle modifications (diet, exercise) crucial for symptom management",
                    "Consider hormone replacement therapy consultation with gynecologist"
                ]
            },

            // Category 6: Men's Health & Urology
            {
                name: "Benign Prostatic Hyperplasia",
                category: "mens",
                systems: ["Urogenital System", "Endocrine System"],
                whatItIs: "Benign Prostatic Hyperplasia (BPH) is non-cancerous enlargement of the prostate gland that commonly occurs with aging, causing urinary symptoms due to compression of the urethra.",
                howItAffects: "Causes urinary frequency, urgency, weak stream, incomplete emptying, and nocturia. Can lead to urinary retention, bladder stones, kidney damage, and significantly reduced quality of life.",
                etalons: {
                    primaryOrgan: ["Prostate gland", "Bladder", "Urethra", "Bladder neck", "Detrusor muscle"],
                    pathomorphology: ["Prostatic hyperplasia", "Urethral compression", "Bladder outlet obstruction", "Detrusor hypertrophy"],
                    associatedSystems: ["Endocrine system", "Nervous system", "Vascular system"],
                    biochemical: ["DHT", "Testosterone", "PSA", "Growth factors", "Inflammatory markers"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in prostate etalons indicate chronic enlargement. Red triangles suggest acute urinary obstruction. Black squares indicate severe bladder dysfunction.",
                    graphNumbers: "Numbers 4-5 in prostate etalons indicate enlargement. Numbers 5-6 in bladder etalons suggest obstruction effects.",
                    anabolismCatabolism: "Red catabolism in obstructed bladder tissue. Blue anabolism hyperactive in prostatic growth.",
                    isoline: "Mild BPH range 0.3-0.5, moderate BPH 0.5-0.7, severe BPH 0.7-0.85",
                    kccValues: "KCC < 0.4 for prostatic hyperplasia etalons indicates active BPH. Healthy prostate etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established prostatic changes",
                    biochemicalHomeostasis: "E values 1 or 7 in DHT and growth factor etalons indicate significant hyperplasia",
                    vegetativeTest: "+12% or more strengthening with prostate-shrinking and urinary flow preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete urogenital assessment with focus on prostate size and urinary flow patterns",
                    focusedAnalysis: "Detailed analysis of prostatic enlargement, bladder function, and urinary obstruction severity",
                    metaTherapy: {
                        selection: "Select prostatic hyperplasia etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 20-25 minutes per session",
                        sessions: "2-3 sessions per week, monitor urinary symptoms and flow",
                        focus: "Maximum 3-4 urogenital etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with prostate-supporting, anti-inflammatory, and urinary flow preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 8-12 weeks per cycle"
                },
                steps: [
                    "Prostate and bladder function assessment",
                    "Analysis of urinary obstruction and flow patterns",
                    "Meta-therapy on prostatic hyperplasia etalons",
                    "Vegetative testing of prostate support preparations",
                    "Urinary symptom improvement evaluation"
                ],
                targets: ["Prostate gland", "Bladder", "Urethra", "Detrusor muscle"],
                notes: [
                    "CRITICAL: Monitor for urinary retention - seek immediate care if unable to urinate",
                    "PSA monitoring important to rule out prostate cancer",
                    "Avoid decongestants and antihistamines which can worsen symptoms",
                    "Consider urological evaluation for severe symptoms"
                ]
            },
            {
                name: "Erectile Dysfunction",
                category: "mens",
                systems: ["Vascular System", "Nervous System"],
                whatItIs: "Erectile Dysfunction (ED) is the inability to achieve or maintain an erection sufficient for sexual intercourse. Can be caused by vascular, neurological, hormonal, or psychological factors.",
                howItAffects: "Causes inability to achieve erections, reduced sexual confidence, relationship stress, and depression. Can indicate underlying cardiovascular disease, diabetes, or hormonal imbalances.",
                etalons: {
                    primaryOrgan: ["Penile blood vessels", "Corpus cavernosum", "Penile nerves", "Endothelium", "Smooth muscle"],
                    pathomorphology: ["Vascular insufficiency", "Endothelial dysfunction", "Nerve damage", "Smooth muscle fibrosis"],
                    associatedSystems: ["Cardiovascular system", "Endocrine system", "Nervous system", "Psychological factors"],
                    biochemical: ["Nitric oxide", "cGMP", "Testosterone", "Endothelin", "PDE5", "Vascular mediators"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in penile vascular etalons indicate chronic dysfunction. Red triangles suggest acute vascular compromise. Black squares indicate severe erectile failure.",
                    graphNumbers: "Numbers 4-6 in vascular etalons indicate blood flow problems. Numbers 5-6 in nerve etalons suggest neurological involvement.",
                    anabolismCatabolism: "Red catabolism in damaged penile tissue. Blue anabolism reduced in vascular repair mechanisms.",
                    isoline: "Mild ED range 0.3-0.5, moderate ED 0.5-0.7, severe ED 0.7-0.85",
                    kccValues: "KCC < 0.4 for erectile function etalons indicates active ED. Healthy erectile etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established vascular changes",
                    biochemicalHomeostasis: "E values 1 or 7 in nitric oxide and testosterone etalons indicate significant dysfunction",
                    vegetativeTest: "+12% or more strengthening with vascular and erectile function preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete erectile function assessment with focus on vascular and neurological factors",
                    focusedAnalysis: "Detailed analysis of penile blood flow, nerve function, and hormonal influences",
                    metaTherapy: {
                        selection: "Select erectile dysfunction etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 20-25 minutes per session",
                        sessions: "2-3 sessions per week, monitor erectile function improvement",
                        focus: "Maximum 3-4 erectile function etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with vascular-enhancing, nerve-supporting, and hormone-balancing preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 2x daily) or sugar pellets (3 pellets 2x daily). Duration: 6-10 weeks per cycle"
                },
                steps: [
                    "Erectile function and vascular assessment",
                    "Analysis of blood flow and nerve function",
                    "Meta-therapy on erectile dysfunction etalons",
                    "Vegetative testing of sexual health preparations",
                    "Erectile function improvement evaluation"
                ],
                targets: ["Penile blood vessels", "Corpus cavernosum", "Penile nerves", "Endothelium"],
                notes: [
                    "CRITICAL: May indicate cardiovascular disease - comprehensive health evaluation recommended",
                    "Lifestyle modifications (exercise, diet, smoking cessation) crucial",
                    "Psychological counseling may be beneficial",
                    "Coordinate with urologist for comprehensive treatment approach"
                ]
            },

            // Category 7: Pediatric & Child Health
            {
                name: "ADHD in Children",
                category: "pediatric",
                systems: ["Nervous System", "Behavioral System"],
                whatItIs: "Attention Deficit Hyperactivity Disorder (ADHD) in children is a neurodevelopmental condition characterized by inattention, hyperactivity, and impulsivity that interferes with development and functioning.",
                howItAffects: "Causes difficulty focusing, hyperactive behavior, impulsiveness, and academic problems. Can lead to social difficulties, low self-esteem, family stress, and long-term educational challenges.",
                etalons: {
                    primaryOrgan: ["Prefrontal cortex", "Basal ganglia", "Cerebellum", "Neurotransmitter pathways", "Attention networks"],
                    pathomorphology: ["Executive function deficits", "Dopamine dysregulation", "Neural connectivity issues", "Attention network dysfunction"],
                    associatedSystems: ["Endocrine system", "Sleep regulation", "Sensory processing", "Motor control"],
                    biochemical: ["Dopamine", "Norepinephrine", "GABA", "Acetylcholine", "Stress hormones"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in attention network etalons indicate chronic dysfunction. Red triangles suggest acute behavioral episodes. Black squares indicate severe executive dysfunction.",
                    graphNumbers: "Numbers 4-5 in prefrontal etalons indicate attention deficits. Numbers 5-6 in dopamine etalons suggest neurotransmitter imbalance.",
                    anabolismCatabolism: "Red catabolism in stress response during behavioral episodes. Blue anabolism disrupted in neural development.",
                    isoline: "Mild ADHD range 0.3-0.5, moderate ADHD 0.5-0.7, severe ADHD 0.7-0.85",
                    kccValues: "KCC < 0.4 for attention deficit etalons indicates active ADHD. Healthy attention etalons show KCC > 0.8",
                    entropyAnalysis: "E values 3-5 in pathomorphology etalons indicate developmental attention changes",
                    biochemicalHomeostasis: "E values 1 or 7 in dopamine and attention etalons indicate significant dysfunction",
                    vegetativeTest: "+10% or more strengthening with attention-enhancing and behavioral-balancing preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete neurodevelopmental assessment with focus on attention networks and executive function",
                    focusedAnalysis: "Detailed analysis of attention deficits, hyperactivity patterns, and neurotransmitter balance",
                    metaTherapy: {
                        selection: "Select attention deficit etalons with highest activity (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 15-20 minutes per session (shorter for children)",
                        sessions: "2 sessions per week, monitor behavioral improvements and attention span",
                        focus: "Maximum 2-3 attention-related etalons per session for children"
                    },
                    vegetativeTest: "Test energetic compatibility with attention-enhancing, behavioral-calming, and neurodevelopmental preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (2 pellets 3x daily). Duration: 6-8 weeks per cycle"
                },
                steps: [
                    "Neurodevelopmental and attention assessment",
                    "Analysis of behavioral patterns and executive function",
                    "Meta-therapy on attention enhancement etalons",
                    "Vegetative testing of behavioral support preparations",
                    "Attention and behavior improvement evaluation"
                ],
                targets: ["Prefrontal cortex", "Attention networks", "Dopamine pathways", "Executive function"],
                notes: [
                    "CRITICAL: Coordinate with pediatrician and child psychologist for comprehensive care",
                    "Behavioral interventions and structure crucial for success",
                    "Diet modifications may help reduce hyperactivity",
                    "School accommodation plans often necessary for academic success"
                ]
            },
            {
                name: "Childhood Allergies",
                category: "pediatric",
                systems: ["Immune System", "Respiratory System"],
                whatItIs: "Childhood allergies involve immune system overreactions to normally harmless substances like foods, environmental allergens, or medications, causing various symptoms from mild to severe.",
                howItAffects: "Causes sneezing, runny nose, skin rashes, digestive upset, and breathing difficulties. Can lead to asthma development, food restrictions, social limitations, and life-threatening anaphylaxis.",
                etalons: {
                    primaryOrgan: ["Immune cells", "Respiratory tract", "Skin", "Digestive tract", "Lymph nodes"],
                    pathomorphology: ["IgE-mediated reactions", "Mast cell activation", "Inflammatory cascades", "Tissue hypersensitivity"],
                    associatedSystems: ["Respiratory system", "Dermatological system", "Digestive system", "Nervous system"],
                    biochemical: ["IgE antibodies", "Histamine", "Leukotrienes", "Inflammatory cytokines", "Complement system"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in immune etalons indicate chronic hypersensitivity. Red triangles suggest acute allergic reactions. Black squares indicate severe immune dysfunction.",
                    graphNumbers: "Numbers 5-6 in IgE etalons indicate high sensitivity. Numbers 4-5 in inflammatory etalons suggest active allergic response.",
                    anabolismCatabolism: "Red catabolism during allergic reactions. Blue anabolism disrupted in immune tolerance mechanisms.",
                    isoline: "Mild allergies range 0.3-0.5, moderate allergies 0.5-0.7, severe allergies 0.7-0.9",
                    kccValues: "KCC < 0.4 for allergic response etalons indicates active allergies. Healthy immune tolerance etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established allergic patterns",
                    biochemicalHomeostasis: "E values 1 or 7 in IgE and histamine etalons indicate significant allergic activity",
                    vegetativeTest: "+12% or more strengthening with immune-balancing and anti-allergic preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete immune system assessment with focus on allergic sensitivity patterns and trigger identification",
                    focusedAnalysis: "Detailed analysis of IgE responses, inflammatory cascades, and organ system involvement",
                    metaTherapy: {
                        selection: "Select allergic response etalons with highest activity (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 15-20 minutes per session (child-appropriate)",
                        sessions: "2-3 sessions per week, monitor allergic symptoms and trigger responses",
                        focus: "Maximum 3 allergic response etalons per session for children"
                    },
                    vegetativeTest: "Test energetic compatibility with immune-balancing, anti-histamine, and tolerance-building preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (2 pellets 3x daily). Duration: 4-8 weeks per cycle"
                },
                steps: [
                    "Comprehensive allergic sensitivity assessment",
                    "Analysis of immune responses and trigger patterns",
                    "Meta-therapy on allergic reaction etalons",
                    "Vegetative testing of immune balance preparations",
                    "Allergic symptom reduction evaluation"
                ],
                targets: ["Immune cells", "IgE antibodies", "Mast cells", "Inflammatory mediators"],
                notes: [
                    "CRITICAL: Identify and avoid known allergens completely",
                    "Emergency action plan essential for severe allergies",
                    "EpiPen training for anaphylaxis risk",
                    "Coordinate with pediatric allergist for comprehensive management"
                ]
            },

            // Category 8: Geriatric & Age-Related
            {
                name: "Age-Related Cognitive Decline",
                category: "geriatric",
                systems: ["Nervous System", "Vascular System"],
                whatItIs: "Age-related cognitive decline involves gradual changes in memory, processing speed, and executive function that occur with normal aging, distinct from dementia but may progress to mild cognitive impairment.",
                howItAffects: "Causes memory lapses, slower thinking, difficulty multitasking, and word-finding problems. Can lead to functional decline, loss of independence, social isolation, and increased dementia risk.",
                etalons: {
                    primaryOrgan: ["Hippocampus", "Prefrontal cortex", "Cerebral blood vessels", "Neurons", "Synapses"],
                    pathomorphology: ["Neuronal atrophy", "Reduced synaptic density", "Vascular changes", "Oxidative damage", "Protein aggregation"],
                    associatedSystems: ["Cardiovascular system", "Endocrine system", "Immune system", "Sleep regulation"],
                    biochemical: ["Neurotransmitters", "BDNF", "Amyloid proteins", "Tau proteins", "Antioxidants", "Inflammatory markers"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in cognitive etalons indicate chronic decline. Red triangles suggest acute cognitive episodes. Black squares indicate severe neurodegeneration.",
                    graphNumbers: "Numbers 4-5 in memory etalons indicate decline. Numbers 5-6 in vascular etalons suggest reduced brain perfusion.",
                    anabolismCatabolism: "Red catabolism in aging brain tissue. Blue anabolism reduced in neuroplasticity and repair mechanisms.",
                    isoline: "Normal aging range 0.2-0.4, mild decline 0.4-0.6, significant decline 0.6-0.8",
                    kccValues: "KCC < 0.5 for cognitive decline etalons indicates active aging changes. Healthy cognitive etalons show KCC > 0.8",
                    entropyAnalysis: "E values 3-5 in pathomorphology etalons indicate age-related brain changes",
                    biochemicalHomeostasis: "E values 1 or 7 in neurotransmitter and BDNF etalons indicate significant decline",
                    vegetativeTest: "+10% or more strengthening with cognitive-enhancing and neuroprotective preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete cognitive assessment with focus on memory, executive function, and brain vascular health",
                    focusedAnalysis: "Detailed analysis of cognitive domains, neuroplasticity markers, and vascular perfusion patterns",
                    metaTherapy: {
                        selection: "Select cognitive decline etalons with highest activity (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 25-30 minutes per session",
                        sessions: "2-3 sessions per week, monitor cognitive function and daily activities",
                        focus: "Maximum 3-4 cognitive etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with cognitive-enhancing, neuroprotective, and circulation-improving preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 8-12 weeks per cycle"
                },
                steps: [
                    "Comprehensive cognitive function assessment",
                    "Analysis of memory, attention, and executive function",
                    "Meta-therapy on cognitive enhancement etalons",
                    "Vegetative testing of brain health preparations",
                    "Cognitive improvement and function evaluation"
                ],
                targets: ["Hippocampus", "Prefrontal cortex", "Cerebral blood vessels", "Synapses"],
                notes: [
                    "CRITICAL: Mental stimulation and social engagement crucial for cognitive health",
                    "Regular physical exercise excellent for brain health",
                    "Mediterranean diet beneficial for cognitive function",
                    "Monitor for progression to mild cognitive impairment or dementia"
                ]
            },
            {
                name: "Osteoporosis",
                category: "geriatric",
                systems: ["Skeletal System", "Endocrine System"],
                whatItIs: "Osteoporosis is a bone disease characterized by low bone mass and deterioration of bone tissue, leading to increased fracture risk. Most common in postmenopausal women and elderly individuals.",
                howItAffects: "Causes bone fragility, increased fracture risk, height loss, and spinal deformity. Can lead to hip fractures, vertebral compression fractures, disability, and increased mortality risk.",
                etalons: {
                    primaryOrgan: ["Bone matrix", "Osteoblasts", "Osteoclasts", "Bone marrow", "Trabecular bone"],
                    pathomorphology: ["Bone density loss", "Trabecular thinning", "Cortical porosity", "Microarchitecture deterioration"],
                    associatedSystems: ["Endocrine system", "Digestive system", "Renal system", "Muscular system"],
                    biochemical: ["Calcium", "Vitamin D", "PTH", "Bone turnover markers", "Estrogen", "Testosterone"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in bone density etalons indicate chronic loss. Red triangles suggest acute bone resorption. Black squares indicate severe osteoporosis.",
                    graphNumbers: "Numbers 5-6 in bone density etalons indicate significant loss. Numbers 4-5 in calcium etalons suggest deficiency.",
                    anabolismCatabolism: "Red catabolism predominant in bone resorption. Blue anabolism severely reduced in bone formation.",
                    isoline: "Osteopenia range 0.4-0.6, mild osteoporosis 0.6-0.8, severe osteoporosis 0.8-0.9",
                    kccValues: "KCC < 0.3 for bone density etalons indicates severe osteoporosis. Healthy bone etalons show KCC > 0.8",
                    entropyAnalysis: "E values 5-6 in pathomorphology etalons indicate established bone loss",
                    biochemicalHomeostasis: "E values 1 or 7 in calcium and vitamin D etalons indicate significant deficiency",
                    vegetativeTest: "+12% or more strengthening with bone-building and calcium-enhancing preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete skeletal assessment with focus on bone density and mineral metabolism",
                    focusedAnalysis: "Detailed analysis of bone formation, resorption balance, and fracture risk factors",
                    metaTherapy: {
                        selection: "Select bone density loss etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 25-30 minutes per session",
                        sessions: "2-3 sessions per week, monitor bone density and fracture risk",
                        focus: "Maximum 3-4 bone health etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with bone-building, calcium-enhancing, and fracture-preventing preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily with meals) or sugar pellets (3 pellets 3x daily). Duration: 12-16 weeks per cycle"
                },
                steps: [
                    "Bone density and mineral metabolism assessment",
                    "Analysis of bone formation and resorption balance",
                    "Meta-therapy on bone density enhancement etalons",
                    "Vegetative testing of bone health preparations",
                    "Bone density improvement and fracture risk evaluation"
                ],
                targets: ["Bone matrix", "Osteoblasts", "Osteoclasts", "Calcium metabolism"],
                notes: [
                    "CRITICAL: Weight-bearing exercise essential for bone health",
                    "Adequate calcium and vitamin D intake crucial",
                    "Fall prevention strategies important to reduce fracture risk",
                    "Regular bone density monitoring with DEXA scans recommended"
                ]
            },

            // CARDIOVASCULAR SYSTEM - Complete Version 53 Disease List
            {
                name: "Hypertension",
                category: "cardiovascular",
                systems: ["Cardiovascular System"],
                whatItIs: "Hypertension is a chronic condition characterized by persistently elevated blood pressure (≥140/90 mmHg). It's often called the 'silent killer' as it typically presents without symptoms until complications develop.",
                howItAffects: "Causes headaches, dizziness, chest pain, and shortness of breath. Long-term complications include heart disease, stroke, kidney damage, and retinal damage. Can lead to heart failure and arterial damage.",
                etalons: {
                    primaryOrgan: ["Heart", "Arteries", "Kidneys", "Adrenal glands"],
                    pathomorphology: ["Arterial wall thickening", "Atherosclerotic plaques", "Left ventricular hypertrophy"],
                    associatedSystems: ["Nervous system", "Endocrine system", "Renal system"],
                    biochemical: ["Renin-angiotensin system", "Aldosterone", "Catecholamines", "Nitric oxide"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in cardiovascular etalons indicate chronic energetic stress. Red triangles suggest acute vascular tension. Black squares indicate severe energetic depletion.",
                    graphNumbers: "Numbers 4-5 in arterial etalons indicate significant energetic deviation from normal vascular tone.",
                    anabolismCatabolism: "Red catabolism lines predominant in vascular smooth muscle, indicating breakdown processes. Blue anabolism reduced in arterial repair mechanisms.",
                    isoline: "Chronic process range 0.3-0.6, acute hypertensive episodes 0.7-0.9",
                    kccValues: "KCC < 0.425 for pathological vascular etalons indicates high similarity to hypertensive patterns. Healthy arterial etalons show KCC > 0.7",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate mature hypertensive changes",
                    biochemicalHomeostasis: "E values 1 or 7 in renin-angiotensin etalons indicate significant deviation",
                    vegetativeTest: "+10% or more strengthening with antihypertensive preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete cardiovascular system scan with focus on arterial tree and cardiac function",
                    focusedAnalysis: "Detailed analysis of arterial wall etalons, cardiac output patterns, and renal function markers",
                    metaTherapy: {
                        selection: "Select arterial wall etalons with highest energetic stress (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 15-20 minutes per session",
                        sessions: "2-3 sessions per week, monitor blood pressure changes after each session",
                        focus: "Maximum 3-4 etalons per session to avoid energetic overload"
                    },
                    vegetativeTest: "Test energetic compatibility with cardiovascular support preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 2-3 weeks per imprinting cycle"
                },
                steps: [
                    "Initial comprehensive cardiovascular scan",
                    "Analysis of arterial walls and blood flow patterns",
                    "Meta-therapy on highest stress arterial etalons",
                    "Vegetative testing of cardiovascular preparations",
                    "Frequency imprinting and follow-up assessment"
                ],
                targets: ["Arterial walls", "Smooth muscle cells", "Kidneys", "Adrenal glands"],
                notes: [
                    "CRITICAL: Ongoing medical monitoring essential - never discontinue prescribed medications",
                    "Monitor blood pressure before and after each session",
                    "Coordinate with cardiologist for medication adjustments",
                    "Regular energetic follow-up every 2-3 weeks recommended"
                ]
            },
            {
                name: "Coronary Artery Disease",
                category: "cardiovascular",
                systems: ["Cardiovascular System"],
                whatItIs: "Coronary Artery Disease (CAD) is the narrowing or blockage of coronary arteries due to atherosclerotic plaque buildup, reducing blood flow to the heart muscle.",
                howItAffects: "Causes chest pain (angina), shortness of breath, fatigue, and heart palpitations. Can lead to heart attack, heart failure, arrhythmias, and sudden cardiac death.",
                etalons: {
                    primaryOrgan: ["Coronary arteries", "Heart muscle", "Left ventricle", "Right ventricle", "Cardiac conduction system"],
                    pathomorphology: ["Atherosclerotic plaques", "Arterial stenosis", "Myocardial ischemia", "Collateral circulation"],
                    associatedSystems: ["Vascular system", "Lipid metabolism", "Inflammatory system"],
                    biochemical: ["Cholesterol", "LDL", "HDL", "Troponins", "CRP", "Homocysteine"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in coronary etalons indicate chronic stenosis. Red triangles suggest acute ischemia. Black squares indicate severe blockage.",
                    graphNumbers: "Numbers 5-6 in coronary artery etalons indicate significant stenosis. Numbers 4-5 in myocardial etalons suggest ischemia.",
                    anabolismCatabolism: "Red catabolism in ischemic myocardium. Blue anabolism reduced in cardiac repair mechanisms.",
                    isoline: "Mild CAD range 0.3-0.5, moderate CAD 0.5-0.7, severe CAD 0.7-0.9",
                    kccValues: "KCC < 0.4 for coronary stenosis etalons indicates significant CAD. Healthy coronary etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate established atherosclerotic changes",
                    biochemicalHomeostasis: "E values 1 or 7 in lipid and inflammatory etalons indicate significant cardiovascular risk",
                    vegetativeTest: "+12% or more strengthening with cardioprotective and circulation-enhancing preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete cardiac assessment with focus on coronary circulation and myocardial perfusion",
                    focusedAnalysis: "Detailed analysis of coronary stenosis, collateral circulation, and myocardial viability",
                    metaTherapy: {
                        selection: "Select coronary stenosis etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 20-25 minutes per session",
                        sessions: "2-3 sessions per week, monitor cardiac symptoms and exercise tolerance",
                        focus: "Maximum 3-4 cardiac etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with cardioprotective, circulation-enhancing, and anti-atherosclerotic preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 8-12 weeks per cycle"
                },
                steps: [
                    "Coronary circulation assessment",
                    "Analysis of atherosclerotic burden and stenosis severity",
                    "Meta-therapy on coronary stenosis etalons",
                    "Vegetative testing of cardioprotective preparations",
                    "Cardiac function and symptom evaluation"
                ],
                targets: ["Coronary arteries", "Heart muscle", "Cardiac conduction system"],
                notes: [
                    "CRITICAL: Coordinate with cardiologist - never discontinue cardiac medications",
                    "Monitor for chest pain, shortness of breath, or cardiac symptoms",
                    "Lifestyle modifications (diet, exercise, smoking cessation) essential",
                    "Regular cardiac monitoring and stress testing recommended"
                ]
            },
            {
                name: "Heart Failure",
                category: "cardiovascular",
                systems: ["Cardiovascular System"],
                whatItIs: "Heart Failure is a chronic condition where the heart cannot pump blood effectively to meet the body's needs. Can be systolic (reduced ejection fraction) or diastolic (preserved ejection fraction).",
                howItAffects: "Causes shortness of breath, fatigue, swelling in legs and abdomen, and reduced exercise tolerance. Can lead to pulmonary edema, kidney dysfunction, and increased mortality risk.",
                etalons: {
                    primaryOrgan: ["Left ventricle", "Right ventricle", "Heart valves", "Cardiac muscle", "Conduction system"],
                    pathomorphology: ["Ventricular dysfunction", "Cardiac remodeling", "Myocardial fibrosis", "Valve insufficiency"],
                    associatedSystems: ["Pulmonary system", "Renal system", "Vascular system", "Neurohormonal system"],
                    biochemical: ["BNP", "NT-proBNP", "Troponins", "Renin", "Angiotensin", "Aldosterone"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in ventricular etalons indicate chronic dysfunction. Red triangles suggest acute decompensation. Black squares indicate severe heart failure.",
                    graphNumbers: "Numbers 5-6 in cardiac function etalons indicate significant impairment. Numbers 4-5 in compensation etalons suggest adaptive mechanisms.",
                    anabolismCatabolism: "Red catabolism in failing myocardium. Blue anabolism compromised in cardiac repair and remodeling.",
                    isoline: "Compensated HF range 0.4-0.6, decompensated HF 0.6-0.8, end-stage HF 0.8-0.95",
                    kccValues: "KCC < 0.3 for heart failure etalons indicates severe dysfunction. Healthy cardiac etalons show KCC > 0.8",
                    entropyAnalysis: "E values 5-6 in pathomorphology etalons indicate advanced cardiac remodeling",
                    biochemicalHomeostasis: "E values 1 or 7 in neurohormonal etalons indicate significant activation",
                    vegetativeTest: "+10% or more strengthening with cardiac support and diuretic preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete cardiac function assessment with focus on ventricular performance and compensation mechanisms",
                    focusedAnalysis: "Detailed analysis of systolic/diastolic function, cardiac output, and neurohormonal activation",
                    metaTherapy: {
                        selection: "Select heart failure etalons with highest dysfunction (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 25-30 minutes per session",
                        sessions: "2 sessions per week, monitor symptoms and fluid status closely",
                        focus: "Maximum 2-3 cardiac etalons per session to prevent overload"
                    },
                    vegetativeTest: "Test energetic compatibility with cardiac support, diuretic, and neurohormonal modulating preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily) or sugar pellets (4 pellets 3x daily). Duration: 10-16 weeks per cycle"
                },
                steps: [
                    "Cardiac function and compensation assessment",
                    "Analysis of ventricular performance and remodeling",
                    "Meta-therapy on heart failure etalons",
                    "Vegetative testing of cardiac support preparations",
                    "Heart failure symptom and function evaluation"
                ],
                targets: ["Left ventricle", "Right ventricle", "Heart valves", "Cardiac muscle"],
                notes: [
                    "CRITICAL: Daily weight monitoring essential - report 2-3 lb gain in 24 hours",
                    "Fluid and sodium restriction crucial for management",
                    "Never discontinue heart failure medications without cardiology consultation",
                    "Monitor for signs of decompensation (increased shortness of breath, swelling)"
                ]
            },
            {
                name: "Atrial Fibrillation",
                category: "cardiovascular",
                systems: ["Cardiovascular System"],
                whatItIs: "Atrial Fibrillation (AFib) is an irregular heart rhythm caused by chaotic electrical activity in the atria, leading to ineffective atrial contraction and irregular ventricular response.",
                howItAffects: "Causes palpitations, shortness of breath, fatigue, chest discomfort, and dizziness. Can lead to stroke, heart failure, and increased mortality risk due to blood clot formation.",
                etalons: {
                    primaryOrgan: ["Atria", "AV node", "Pulmonary veins", "Cardiac conduction system", "Left atrial appendage"],
                    pathomorphology: ["Atrial remodeling", "Electrical chaos", "Fibrosis", "Thrombosis risk"],
                    associatedSystems: ["Nervous system", "Thyroid system", "Vascular system"],
                    biochemical: ["Electrolytes", "Thyroid hormones", "Inflammatory markers", "Coagulation factors"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in atrial etalons indicate chronic remodeling. Red triangles suggest acute AFib episodes. Black squares indicate permanent AFib.",
                    graphNumbers: "Numbers 5-6 in conduction system etalons indicate electrical instability. Numbers 4-5 in atrial etalons suggest structural changes.",
                    anabolismCatabolism: "Red catabolism in electrically unstable atria. Blue anabolism disrupted in normal conduction pathways.",
                    isoline: "Paroxysmal AFib range 0.3-0.5, persistent AFib 0.5-0.7, permanent AFib 0.7-0.85",
                    kccValues: "KCC < 0.4 for atrial fibrillation etalons indicates active AFib. Healthy rhythm etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established atrial changes",
                    biochemicalHomeostasis: "E values 1 or 7 in electrolyte and thyroid etalons indicate triggering factors",
                    vegetativeTest: "+12% or more strengthening with rhythm-stabilizing and anticoagulant preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete cardiac rhythm assessment with focus on atrial function and electrical stability",
                    focusedAnalysis: "Detailed analysis of atrial remodeling, conduction patterns, and stroke risk factors",
                    metaTherapy: {
                        selection: "Select atrial fibrillation etalons with highest electrical instability (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 20-25 minutes per session",
                        sessions: "2-3 sessions per week, monitor rhythm and symptoms",
                        focus: "Maximum 3 cardiac rhythm etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with rhythm-stabilizing, rate-controlling, and stroke prevention preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 6-10 weeks per cycle"
                },
                steps: [
                    "Cardiac rhythm and atrial function assessment",
                    "Analysis of electrical conduction and remodeling patterns",
                    "Meta-therapy on atrial fibrillation etalons",
                    "Vegetative testing of rhythm control preparations",
                    "Rhythm stability and stroke risk evaluation"
                ],
                targets: ["Atria", "AV node", "Pulmonary veins", "Conduction system"],
                notes: [
                    "CRITICAL: Stroke prevention with anticoagulation essential for most patients",
                    "Monitor for symptoms of stroke (sudden weakness, speech changes, vision loss)",
                    "Avoid excessive alcohol and caffeine which can trigger AFib",
                    "Regular INR monitoring if on warfarin, or follow anticoagulant protocols"
                ]
            },
            {
                name: "Peripheral Artery Disease",
                category: "cardiovascular",
                systems: ["Cardiovascular System", "Vascular System"],
                whatItIs: "Peripheral Artery Disease (PAD) is atherosclerotic narrowing of arteries supplying the extremities, most commonly the legs, reducing blood flow and oxygen delivery to tissues.",
                howItAffects: "Causes leg pain with walking (claudication), cold extremities, slow wound healing, and muscle weakness. Can lead to critical limb ischemia, gangrene, and amputation.",
                etalons: {
                    primaryOrgan: ["Peripheral arteries", "Leg muscles", "Foot circulation", "Collateral vessels"],
                    pathomorphology: ["Arterial stenosis", "Atherosclerotic plaques", "Tissue ischemia", "Muscle atrophy"],
                    associatedSystems: ["Muscular system", "Integumentary system", "Nervous system"],
                    biochemical: ["Ankle-brachial index", "Inflammatory markers", "Lipid profile", "Homocysteine"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in peripheral artery etalons indicate chronic stenosis. Red triangles suggest acute ischemia. Black squares indicate critical limb ischemia.",
                    graphNumbers: "Numbers 5-6 in peripheral circulation etalons indicate significant impairment. Numbers 4-5 in muscle etalons suggest ischemic changes.",
                    anabolismCatabolism: "Red catabolism in ischemic muscle tissue. Blue anabolism reduced in tissue repair and collateral formation.",
                    isoline: "Mild PAD range 0.3-0.5, moderate PAD 0.5-0.7, severe PAD 0.7-0.9",
                    kccValues: "KCC < 0.4 for peripheral stenosis etalons indicates significant PAD. Healthy circulation etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate established peripheral vascular disease",
                    biochemicalHomeostasis: "E values 1 or 7 in circulation and inflammatory etalons indicate significant vascular compromise",
                    vegetativeTest: "+12% or more strengthening with circulation-enhancing and vasodilating preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete peripheral vascular assessment with focus on arterial flow and tissue perfusion",
                    focusedAnalysis: "Detailed analysis of arterial stenosis severity, collateral circulation, and tissue viability",
                    metaTherapy: {
                        selection: "Select peripheral stenosis etalons with highest impairment (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 25-30 minutes per session",
                        sessions: "2-3 sessions per week, monitor walking distance and symptoms",
                        focus: "Maximum 3-4 peripheral vascular etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with circulation-enhancing, vasodilating, and tissue-protective preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 8-12 weeks per cycle"
                },
                steps: [
                    "Peripheral circulation and arterial flow assessment",
                    "Analysis of stenosis severity and tissue perfusion",
                    "Meta-therapy on peripheral vascular etalons",
                    "Vegetative testing of circulation enhancement preparations",
                    "Walking capacity and symptom improvement evaluation"
                ],
                targets: ["Peripheral arteries", "Leg muscles", "Collateral vessels"],
                notes: [
                    "CRITICAL: Smoking cessation absolutely essential for treatment success",
                    "Regular walking exercise program crucial for symptom improvement",
                    "Foot care extremely important to prevent ulcers and infections",
                    "Monitor for signs of critical limb ischemia (rest pain, non-healing wounds)"
                ]
            },

            // RESPIRATORY SYSTEM - Complete Version 53 Disease List
            {
                name: "Asthma",
                category: "respiratory",
                systems: ["Respiratory System"],
                whatItIs: "Asthma is a chronic inflammatory airway disease characterized by variable airflow obstruction, bronchial hyperresponsiveness, and inflammation. Can be allergic, non-allergic, or mixed type.",
                howItAffects: "Causes wheezing, shortness of breath, chest tightness, and coughing. Can lead to respiratory failure, status asthmaticus, and reduced quality of life. Triggers include allergens, infections, and stress.",
                etalons: {
                    primaryOrgan: ["Bronchi", "Bronchioles", "Alveoli", "Respiratory epithelium", "Smooth muscle"],
                    pathomorphology: ["Bronchial inflammation", "Mucus hypersecretion", "Airway remodeling", "Eosinophilic infiltration"],
                    associatedSystems: ["Immune system", "Autonomic nervous system", "Adrenal system"],
                    biochemical: ["IgE", "Histamine", "Leukotrienes", "Cortisol", "Inflammatory cytokines", "Nitric oxide"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in bronchial etalons indicate chronic inflammation. Red triangles suggest acute bronchospasm risk. Black squares indicate severe airway compromise.",
                    graphNumbers: "Numbers 4-5 in bronchiole etalons indicate significant obstruction. Numbers 5-6 in inflammatory etalons suggest active inflammation.",
                    anabolismCatabolism: "Red catabolism predominant in inflamed airways. Blue anabolism reduced in epithelial repair mechanisms.",
                    isoline: "Stable asthma range 0.3-0.5, acute exacerbation 0.7-0.9, status asthmaticus 0.9-0.95",
                    kccValues: "KCC < 0.4 for inflammatory etalons indicates high similarity to asthmatic inflammation. Healthy airway etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate established airway remodeling",
                    biochemicalHomeostasis: "E values 1 or 7 in IgE and inflammatory cytokine etalons indicate significant allergic response",
                    vegetativeTest: "+12% or more strengthening with bronchodilator and anti-inflammatory preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete respiratory system assessment with focus on airway inflammation and bronchial reactivity patterns",
                    focusedAnalysis: "Detailed analysis of bronchial smooth muscle tone, inflammatory markers, and trigger sensitivity patterns",
                    metaTherapy: {
                        selection: "Select bronchial inflammation etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 15-20 minutes per session",
                        sessions: "2-3 sessions per week, monitor peak flow and symptom frequency",
                        focus: "Maximum 3-4 respiratory etalons per session to prevent bronchial irritation"
                    },
                    vegetativeTest: "Test energetic compatibility with bronchodilator, anti-inflammatory, and immune-modulating preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 3-4 weeks per cycle"
                },
                steps: [
                    "Comprehensive respiratory system scan",
                    "Analysis of bronchial reactivity and inflammation",
                    "Meta-therapy on inflammatory airway etalons",
                    "Vegetative testing of respiratory support preparations",
                    "Lung function reassessment"
                ],
                targets: ["Bronchioles", "Alveoli", "Respiratory epithelium", "Smooth muscle"],
                notes: [
                    "CRITICAL: Emergency inhaler must always be available - never discontinue rescue medications",
                    "Monitor peak flow measurements daily during treatment",
                    "Identify and avoid environmental triggers",
                    "Coordinate with pulmonologist for medication adjustments"
                ]
            },
            {
                name: "COPD",
                category: "respiratory",
                systems: ["Respiratory System"],
                whatItIs: "Chronic Obstructive Pulmonary Disease (COPD) is a progressive lung disease characterized by airflow limitation due to emphysema and/or chronic bronchitis, primarily caused by smoking.",
                howItAffects: "Causes chronic cough, sputum production, shortness of breath, and reduced exercise tolerance. Can lead to respiratory failure, cor pulmonale, and increased infection risk.",
                etalons: {
                    primaryOrgan: ["Bronchi", "Bronchioles", "Alveoli", "Lung parenchyma", "Respiratory muscles"],
                    pathomorphology: ["Airway obstruction", "Emphysematous changes", "Chronic inflammation", "Mucus hypersecretion"],
                    associatedSystems: ["Cardiovascular system", "Muscular system", "Immune system"],
                    biochemical: ["Alpha-1 antitrypsin", "Inflammatory cytokines", "Oxidative stress markers", "Arterial blood gases"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in lung etalons indicate chronic damage. Red triangles suggest acute exacerbations. Black squares indicate severe COPD.",
                    graphNumbers: "Numbers 5-6 in airway etalons indicate significant obstruction. Numbers 4-5 in alveolar etalons suggest emphysematous changes.",
                    anabolismCatabolism: "Red catabolism in damaged lung tissue. Blue anabolism severely compromised in lung repair mechanisms.",
                    isoline: "Mild COPD range 0.4-0.6, moderate COPD 0.6-0.8, severe COPD 0.8-0.9",
                    kccValues: "KCC < 0.3 for COPD etalons indicates severe disease. Healthy lung etalons show KCC > 0.8",
                    entropyAnalysis: "E values 5-6 in pathomorphology etalons indicate irreversible lung damage",
                    biochemicalHomeostasis: "E values 1 or 7 in inflammatory and gas exchange etalons indicate significant dysfunction",
                    vegetativeTest: "+10% or more strengthening with bronchodilator and anti-inflammatory preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete pulmonary assessment with focus on airway obstruction and gas exchange patterns",
                    focusedAnalysis: "Detailed analysis of emphysematous changes, airway inflammation, and respiratory muscle function",
                    metaTherapy: {
                        selection: "Select COPD etalons with highest dysfunction (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 20-25 minutes per session",
                        sessions: "2 sessions per week, monitor lung function and symptoms",
                        focus: "Maximum 2-3 respiratory etalons per session to prevent respiratory fatigue"
                    },
                    vegetativeTest: "Test energetic compatibility with bronchodilator, anti-inflammatory, and respiratory support preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily) or sugar pellets (4 pellets 3x daily). Duration: 10-16 weeks per cycle"
                },
                steps: [
                    "Pulmonary function and airway assessment",
                    "Analysis of emphysematous changes and inflammation",
                    "Meta-therapy on COPD etalons",
                    "Vegetative testing of respiratory support preparations",
                    "Lung function and symptom evaluation"
                ],
                targets: ["Bronchi", "Bronchioles", "Alveoli", "Respiratory muscles"],
                notes: [
                    "CRITICAL: Smoking cessation absolutely essential - disease progression continues with smoking",
                    "Oxygen therapy may be needed for severe cases",
                    "Pulmonary rehabilitation programs highly beneficial",
                    "Monitor for signs of respiratory failure or cor pulmonale"
                ]
            },
            {
                name: "Pneumonia",
                category: "respiratory",
                systems: ["Respiratory System", "Immune System"],
                whatItIs: "Pneumonia is an infection of the lungs that inflames air sacs in one or both lungs, which may fill with fluid or pus. Can be caused by bacteria, viruses, or fungi.",
                howItAffects: "Causes cough with phlegm, fever, chills, and difficulty breathing. Can lead to respiratory failure, sepsis, lung abscess, and pleural effusion.",
                etalons: {
                    primaryOrgan: ["Alveoli", "Lung parenchyma", "Bronchioles", "Pleura", "Immune cells"],
                    pathomorphology: ["Alveolar inflammation", "Fluid accumulation", "Consolidation", "Immune infiltration"],
                    associatedSystems: ["Immune system", "Cardiovascular system", "Lymphatic system"],
                    biochemical: ["White blood cells", "C-reactive protein", "Procalcitonin", "Inflammatory cytokines"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in lung etalons indicate chronic infection. Red triangles suggest acute pneumonia. Black squares indicate severe pneumonia with complications.",
                    graphNumbers: "Numbers 5-6 in alveolar etalons indicate significant inflammation. Numbers 4-5 in immune etalons suggest active infection response.",
                    anabolismCatabolism: "Red catabolism predominant during acute infection. Blue anabolism increases during recovery phase.",
                    isoline: "Mild pneumonia range 0.4-0.6, moderate pneumonia 0.6-0.8, severe pneumonia 0.8-0.95",
                    kccValues: "KCC < 0.3 for pneumonia etalons indicates active severe infection. Healthy lung etalons show KCC > 0.8",
                    entropyAnalysis: "E values 5-6 in pathomorphology etalons indicate acute inflammatory changes",
                    biochemicalHomeostasis: "E values 1 or 7 in immune and inflammatory etalons indicate significant infection response",
                    vegetativeTest: "+15% or more strengthening with antimicrobial and immune support preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete pulmonary infection assessment with focus on inflammatory response and pathogen identification",
                    focusedAnalysis: "Detailed analysis of alveolar inflammation, immune response, and infection severity",
                    metaTherapy: {
                        selection: "Select pneumonia etalons with highest inflammatory activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 15-20 minutes per session",
                        sessions: "Daily sessions during acute phase, monitor temperature and symptoms",
                        focus: "Maximum 3-4 infection-related etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with antimicrobial, immune-boosting, and respiratory support preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily) or sugar pellets (4 pellets 4x daily). Duration: 2-4 weeks acute phase"
                },
                steps: [
                    "Pulmonary infection and inflammation assessment",
                    "Analysis of pathogen type and immune response",
                    "Meta-therapy on pneumonia etalons",
                    "Vegetative testing of antimicrobial preparations",
                    "Recovery and lung function evaluation"
                ],
                targets: ["Alveoli", "Lung parenchyma", "Immune cells", "Respiratory tract"],
                notes: [
                    "CRITICAL: Coordinate with physician for antibiotic therapy - never delay medical treatment",
                    "Monitor for signs of respiratory distress or sepsis",
                    "Adequate hydration and rest essential for recovery",
                    "Vaccination prevention important for high-risk individuals"
                ]
            },
            {
                name: "Pulmonary Embolism",
                category: "respiratory",
                systems: ["Respiratory System", "Cardiovascular System"],
                whatItIs: "Pulmonary Embolism (PE) is a blockage of pulmonary arteries by blood clots, usually originating from deep vein thrombosis in the legs, causing impaired gas exchange and circulation.",
                howItAffects: "Causes sudden shortness of breath, chest pain, rapid heart rate, and coughing up blood. Can lead to pulmonary hypertension, right heart failure, and death.",
                etalons: {
                    primaryOrgan: ["Pulmonary arteries", "Right ventricle", "Lung parenchyma", "Pulmonary capillaries"],
                    pathomorphology: ["Arterial occlusion", "Pulmonary infarction", "Right heart strain", "Gas exchange impairment"],
                    associatedSystems: ["Cardiovascular system", "Coagulation system", "Venous system"],
                    biochemical: ["D-dimer", "Troponins", "BNP", "Coagulation factors", "Arterial blood gases"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in pulmonary artery etalons indicate chronic clots. Red triangles suggest acute PE. Black squares indicate massive PE.",
                    graphNumbers: "Numbers 5-6 in pulmonary circulation etalons indicate significant obstruction. Numbers 4-5 in right heart etalons suggest strain.",
                    anabolismCatabolism: "Red catabolism in areas of pulmonary infarction. Blue anabolism compromised in gas exchange mechanisms.",
                    isoline: "Small PE range 0.4-0.6, moderate PE 0.6-0.8, massive PE 0.8-0.95",
                    kccValues: "KCC < 0.3 for PE etalons indicates active pulmonary embolism. Healthy circulation etalons show KCC > 0.8",
                    entropyAnalysis: "E values 5-6 in pathomorphology etalons indicate acute vascular occlusion",
                    biochemicalHomeostasis: "E values 1 or 7 in coagulation and cardiac strain etalons indicate significant PE",
                    vegetativeTest: "+15% or more strengthening with anticoagulant and circulation-restoring preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete pulmonary circulation assessment with focus on arterial patency and right heart function",
                    focusedAnalysis: "Detailed analysis of clot burden, pulmonary perfusion, and cardiac strain patterns",
                    metaTherapy: {
                        selection: "Select pulmonary embolism etalons with highest obstruction (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 20-25 minutes per session",
                        sessions: "Daily sessions during acute phase, monitor oxygen saturation and symptoms",
                        focus: "Maximum 2-3 PE-related etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with anticoagulant, thrombolytic, and cardiopulmonary support preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily) or sugar pellets (4 pellets 4x daily). Duration: 4-8 weeks acute phase"
                },
                steps: [
                    "Pulmonary circulation and clot assessment",
                    "Analysis of arterial obstruction and cardiac strain",
                    "Meta-therapy on pulmonary embolism etalons",
                    "Vegetative testing of anticoagulation preparations",
                    "Circulation restoration and recovery evaluation"
                ],
                targets: ["Pulmonary arteries", "Right ventricle", "Pulmonary capillaries"],
                notes: [
                    "CRITICAL: Medical emergency - immediate anticoagulation essential",
                    "Monitor for signs of massive PE (hypotension, severe dyspnea)",
                    "Long-term anticoagulation usually required",
                    "DVT prevention measures crucial to prevent recurrence"
                ]
            },

            // DIGESTIVE SYSTEM - Complete Version 53 Disease List
            {
                name: "GERD",
                category: "digestive",
                systems: ["Digestive System"],
                whatItIs: "Gastroesophageal Reflux Disease (GERD) is a chronic condition where stomach acid frequently flows back into the esophagus, causing irritation and inflammation of the esophageal lining.",
                howItAffects: "Causes heartburn, regurgitation, chest pain, difficulty swallowing, and chronic cough. Can lead to esophagitis, Barrett's esophagus, esophageal stricture, and increased esophageal cancer risk.",
                etalons: {
                    primaryOrgan: ["Lower esophageal sphincter", "Esophageal mucosa", "Stomach", "Diaphragm", "Vagus nerve"],
                    pathomorphology: ["Esophagitis", "Mucosal erosion", "Barrett's metaplasia", "Sphincter dysfunction"],
                    associatedSystems: ["Nervous system", "Respiratory system", "Muscular system"],
                    biochemical: ["Gastric acid", "Pepsin", "Bile acids", "Inflammatory mediators", "Mucus production"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in esophageal etalons indicate chronic acid exposure. Red triangles suggest acute reflux episodes. Black squares indicate severe esophageal damage.",
                    graphNumbers: "Numbers 4-5 in LES etalons indicate sphincter dysfunction. Numbers 5-6 in esophageal mucosa suggest severe inflammation.",
                    anabolismCatabolism: "Red catabolism predominant in damaged esophageal tissue. Blue anabolism compromised in mucosal repair.",
                    isoline: "Mild GERD range 0.3-0.5, moderate GERD 0.5-0.7, severe GERD with complications 0.7-0.9",
                    kccValues: "KCC < 0.4 for esophagitis etalons indicates active acid damage. Healthy esophageal etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established esophageal changes",
                    biochemicalHomeostasis: "E values 1 or 7 in acid production etalons indicate significant reflux activity",
                    vegetativeTest: "+12% or more strengthening with acid-suppressing and mucosal healing preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete esophagogastric assessment with focus on sphincter function and acid exposure patterns",
                    focusedAnalysis: "Detailed analysis of LES competency, esophageal motility, and mucosal integrity",
                    metaTherapy: {
                        selection: "Select esophageal inflammation etalons with highest acid damage (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 15-20 minutes per session",
                        sessions: "2-3 sessions per week, monitor symptom frequency and severity",
                        focus: "Maximum 3-4 esophagogastric etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with acid-suppressing, sphincter-strengthening, and mucosal protective preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 30 minutes before meals) or sugar pellets (3 pellets before meals). Duration: 4-6 weeks per cycle"
                },
                steps: [
                    "Esophageal function assessment",
                    "Analysis of acid reflux and mucosal damage",
                    "Meta-therapy on esophageal inflammatory etalons",
                    "Vegetative testing of acid neutralization preparations",
                    "Reflux symptom improvement evaluation"
                ],
                targets: ["Lower esophageal sphincter", "Esophageal mucosa", "Stomach"],
                notes: [
                    "CRITICAL: Lifestyle modifications crucial - elevate head of bed 6-8 inches",
                    "Avoid trigger foods (spicy, acidic, fatty foods)",
                    "Weight loss essential if overweight",
                    "Monitor for complications like Barrett's esophagus"
                ]
            },

            // Category 4: Neurology & CNS
            {
                name: "Migraine",
                category: "neurological",
                systems: ["Neurology & CNS"],
                whatItIs: "Migraine is a complex neurological disorder characterized by recurrent moderate to severe headaches, often with aura. Involves vascular, neurological, and biochemical components with genetic predisposition.",
                howItAffects: "Causes severe throbbing headache, nausea, vomiting, light/sound sensitivity, and visual disturbances. Can lead to chronic daily headache, medication overuse headache, and significant disability.",
                etalons: {
                    primaryOrgan: ["Trigeminal nerve", "Cerebral blood vessels", "Brainstem", "Hypothalamus", "Cortical spreading depression"],
                    pathomorphology: ["Vascular inflammation", "Neural sensitization", "Cortical hyperexcitability", "Neurovascular dysfunction"],
                    associatedSystems: ["Vascular system", "Hormonal system", "Autonomic nervous system"],
                    biochemical: ["Serotonin", "CGRP", "Dopamine", "Magnesium", "Estrogen", "Inflammatory mediators"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in trigeminal etalons indicate chronic sensitization. Red triangles suggest acute migraine episodes. Black squares indicate severe neurological dysfunction.",
                    graphNumbers: "Numbers 4-5 in cerebrovascular etalons indicate vascular instability. Numbers 5-6 in brainstem etalons suggest central sensitization.",
                    anabolismCatabolism: "Red catabolism during migraine attacks. Blue anabolism disrupted in neural recovery mechanisms.",
                    isoline: "Episodic migraine range 0.3-0.6, chronic migraine 0.6-0.8, status migrainosus 0.8-0.9",
                    kccValues: "KCC < 0.4 for migraine trigger etalons indicates high susceptibility. Healthy neural etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established neural sensitization",
                    biochemicalHomeostasis: "E values 1 or 7 in neurotransmitter etalons indicate significant imbalance",
                    vegetativeTest: "+12% or more strengthening with migraine preventive and neurovascular stabilizing preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete neurological assessment with focus on trigeminal system and cerebrovascular reactivity",
                    focusedAnalysis: "Detailed analysis of migraine triggers, neural sensitization patterns, and neurovascular stability",
                    metaTherapy: {
                        selection: "Select trigeminal and vascular etalons with highest sensitization (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 20-25 minutes per session",
                        sessions: "2 sessions per week, monitor headache frequency and intensity",
                        focus: "Maximum 3 neurological etalons per session to prevent overstimulation"
                    },
                    vegetativeTest: "Test energetic compatibility with migraine preventive, neurovascular stabilizing, and trigger-reducing preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily) or sugar pellets (3 pellets 4x daily). Duration: 6-8 weeks per cycle"
                },
                steps: [
                    "Cerebrovascular and neural pathway scan",
                    "Analysis of vascular reactivity and neural sensitization",
                    "Meta-therapy on trigeminal sensitization etalons",
                    "Vegetative testing of neurological balance preparations",
                    "Headache pattern reassessment"
                ],
                targets: ["Trigeminal nerve", "Cerebral blood vessels", "Brainstem"],
                notes: [
                    "CRITICAL: Identify and avoid personal trigger factors",
                    "Maintain detailed headache diary for pattern recognition",
                    "Regular sleep schedule absolutely crucial",
                    "Consider hormonal influences in women"
                ]
            },

            // Category 5: Endocrine System
            {
                name: "Type 2 Diabetes",
                category: "endocrine",
                systems: ["Endocrine System"],
                whatItIs: "Type 2 Diabetes is a chronic metabolic disorder characterized by insulin resistance and progressive beta-cell dysfunction, leading to hyperglycemia. Accounts for 90-95% of all diabetes cases.",
                howItAffects: "Causes polyuria, polydipsia, fatigue, blurred vision, and slow wound healing. Can lead to cardiovascular disease, nephropathy, retinopathy, neuropathy, and increased infection risk.",
                etalons: {
                    primaryOrgan: ["Pancreatic beta cells", "Insulin receptors", "Liver", "Muscle tissue", "Adipose tissue"],
                    pathomorphology: ["Beta-cell dysfunction", "Insulin resistance", "Glucose intolerance", "Metabolic syndrome"],
                    associatedSystems: ["Cardiovascular system", "Renal system", "Nervous system", "Immune system"],
                    biochemical: ["Glucose", "Insulin", "HbA1c", "C-peptide", "Inflammatory markers", "Lipid profile"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in pancreatic etalons indicate chronic beta-cell stress. Red triangles suggest acute glucose spikes. Black squares indicate severe metabolic dysfunction.",
                    graphNumbers: "Numbers 4-6 in insulin receptor etalons indicate resistance. Numbers 5-6 in glucose metabolism etalons suggest poor control.",
                    anabolismCatabolism: "Red catabolism predominant in damaged beta cells. Blue anabolism disrupted in glucose utilization.",
                    isoline: "Pre-diabetes range 0.3-0.5, controlled diabetes 0.5-0.7, uncontrolled diabetes 0.7-0.9",
                    kccValues: "KCC < 0.4 for metabolic dysfunction etalons indicates active diabetes. Healthy metabolism etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate established metabolic changes",
                    biochemicalHomeostasis: "E values 1 or 7 in glucose and insulin etalons indicate significant dysregulation",
                    vegetativeTest: "+12% or more strengthening with glucose-regulating and insulin-sensitizing preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete metabolic assessment with focus on pancreatic function and insulin sensitivity patterns",
                    focusedAnalysis: "Detailed analysis of beta-cell function, insulin resistance patterns, and glucose metabolism efficiency",
                    metaTherapy: {
                        selection: "Select metabolic dysfunction etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 20-25 minutes per session",
                        sessions: "2-3 sessions per week, monitor blood glucose and HbA1c",
                        focus: "Maximum 3-4 metabolic etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with glucose-regulating, insulin-sensitizing, and pancreatic support preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink before meals 3x daily) or sugar pellets (3 pellets before meals). Duration: 6-8 weeks per cycle"
                },
                steps: [
                    "Pancreatic function and glucose metabolism scan",
                    "Analysis of insulin resistance and beta-cell function",
                    "Meta-therapy on metabolic dysfunction etalons",
                    "Vegetative testing of glucose regulation preparations",
                    "Glycemic control assessment"
                ],
                targets: ["Pancreatic beta cells", "Insulin receptors", "Liver", "Muscle tissue"],
                notes: [
                    "CRITICAL: Monitor blood glucose regularly - never discontinue prescribed medications",
                    "Dietary modifications absolutely essential for success",
                    "Regular exercise crucial for insulin sensitivity",
                    "Coordinate with endocrinologist for medication adjustments"
                ]
            },

            // Category 6: Renal & Urinary
            {
                name: "Chronic Kidney Disease",
                category: "renal",
                systems: ["Renal & Urinary System"],
                whatItIs: "Chronic Kidney Disease (CKD) is progressive loss of kidney function over months to years, classified in 5 stages based on GFR. Common causes include diabetes, hypertension, and glomerulonephritis.",
                howItAffects: "Causes fatigue, swelling, shortness of breath, nausea, and decreased urine output. Can lead to end-stage renal disease, cardiovascular complications, bone disease, and electrolyte imbalances.",
                etalons: {
                    primaryOrgan: ["Glomeruli", "Tubules", "Interstitium", "Renal blood vessels", "Nephrons"],
                    pathomorphology: ["Glomerulosclerosis", "Tubular atrophy", "Interstitial fibrosis", "Vascular sclerosis"],
                    associatedSystems: ["Cardiovascular system", "Endocrine system", "Bone metabolism", "Electrolyte balance"],
                    biochemical: ["Creatinine", "BUN", "GFR", "Proteinuria", "Electrolytes", "PTH"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in glomerular etalons indicate chronic damage. Red triangles suggest acute kidney injury. Black squares indicate severe renal failure.",
                    graphNumbers: "Numbers 5-6 in nephron etalons indicate significant loss. Numbers 4-5 in filtration etalons suggest reduced function.",
                    anabolismCatabolism: "Red catabolism predominant in damaged kidney tissue. Blue anabolism severely compromised in repair mechanisms.",
                    isoline: "Stage 1-2 CKD range 0.3-0.5, Stage 3-4 CKD 0.5-0.8, Stage 5 CKD 0.8-0.95",
                    kccValues: "KCC < 0.3 for renal damage etalons indicates advanced CKD. Healthy kidney etalons show KCC > 0.8",
                    entropyAnalysis: "E values 5-6 in pathomorphology etalons indicate irreversible structural changes",
                    biochemicalHomeostasis: "E values 1 or 7 in filtration and electrolyte etalons indicate significant dysfunction",
                    vegetativeTest: "+10% or more strengthening with nephroprotective and detoxification preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete renal assessment with focus on glomerular filtration and tubular function patterns",
                    focusedAnalysis: "Detailed analysis of nephron viability, filtration capacity, and progression markers",
                    metaTherapy: {
                        selection: "Select renal damage etalons with highest dysfunction (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 25-30 minutes per session",
                        sessions: "2 sessions per week, monitor creatinine and GFR closely",
                        focus: "Maximum 2-3 renal etalons per session to prevent overload"
                    },
                    vegetativeTest: "Test energetic compatibility with nephroprotective, detoxification, and electrolyte-balancing preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 4x daily) or sugar pellets (4 pellets 3x daily). Duration: 8-12 weeks per cycle"
                },
                steps: [
                    "Comprehensive renal function assessment",
                    "Analysis of glomerular filtration and tubular function",
                    "Meta-therapy on renal damage etalons",
                    "Vegetative testing of kidney support preparations",
                    "Renal function preservation evaluation"
                ],
                targets: ["Glomeruli", "Tubules", "Interstitium", "Renal blood vessels"],
                notes: [
                    "CRITICAL: Monitor creatinine and GFR regularly - coordinate with nephrologist",
                    "Blood pressure control absolutely crucial for progression prevention",
                    "Protein restriction may be needed in advanced stages",
                    "Avoid nephrotoxic medications and contrast agents"
                ]
            },

            // Category 7: Musculoskeletal
            {
                name: "Osteoarthritis",
                category: "musculoskeletal",
                systems: ["Musculoskeletal System"],
                whatItIs: "Osteoarthritis (OA) is a degenerative joint disease characterized by cartilage breakdown, bone changes, and inflammation. Most common form of arthritis, typically affecting weight-bearing joints.",
                howItAffects: "Causes joint pain, stiffness, swelling, and reduced range of motion. Can lead to joint deformity, disability, and significantly reduced quality of life.",
                etalons: {
                    primaryOrgan: ["Articular cartilage", "Synovial membrane", "Subchondral bone", "Joint capsule", "Ligaments"],
                    pathomorphology: ["Cartilage degeneration", "Bone spurs", "Synovial inflammation", "Joint space narrowing"],
                    associatedSystems: ["Muscular system", "Nervous system", "Vascular system"],
                    biochemical: ["Collagen", "Proteoglycans", "Inflammatory cytokines", "Matrix metalloproteinases", "Hyaluronic acid"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in cartilage etalons indicate chronic degeneration. Red triangles suggest acute inflammatory flares. Black squares indicate severe joint destruction.",
                    graphNumbers: "Numbers 4-6 in cartilage etalons indicate significant loss. Numbers 4-5 in bone etalons suggest remodeling.",
                    anabolismCatabolism: "Red catabolism predominant in degenerating cartilage. Blue anabolism compromised in repair mechanisms.",
                    isoline: "Early OA range 0.3-0.5, moderate OA 0.5-0.7, severe OA 0.7-0.85",
                    kccValues: "KCC < 0.4 for cartilage degeneration etalons indicates active OA. Healthy joint etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate established degenerative changes",
                    biochemicalHomeostasis: "E values 1 or 7 in cartilage matrix etalons indicate significant breakdown",
                    vegetativeTest: "+10% or more strengthening with cartilage-supporting and anti-inflammatory preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete joint assessment with focus on cartilage integrity and inflammatory patterns",
                    focusedAnalysis: "Detailed analysis of cartilage degeneration, bone changes, and synovial inflammation",
                    metaTherapy: {
                        selection: "Select cartilage degeneration etalons with highest activity (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 20-25 minutes per session",
                        sessions: "2-3 sessions per week, monitor pain and mobility",
                        focus: "Maximum 3-4 joint etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with cartilage-supporting, anti-inflammatory, and joint mobility preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 6-8 weeks per cycle"
                },
                steps: [
                    "Joint cartilage and bone assessment",
                    "Analysis of degenerative changes and inflammation",
                    "Meta-therapy on cartilage degeneration etalons",
                    "Vegetative testing of joint support preparations",
                    "Joint function and pain evaluation"
                ],
                targets: ["Articular cartilage", "Synovial membrane", "Subchondral bone"],
                notes: [
                    "CRITICAL: Weight management absolutely essential for weight-bearing joints",
                    "Low-impact exercise beneficial for joint mobility",
                    "Joint protection strategies important",
                    "Consider physical therapy for optimal outcomes"
                ]
            },

            // Category 8: Dermatology
            {
                name: "Eczema",
                category: "dermatology",
                systems: ["Dermatology"],
                whatItIs: "Eczema (Atopic Dermatitis) is a chronic inflammatory skin condition characterized by impaired skin barrier function and immune dysregulation. Often associated with allergies and asthma.",
                howItAffects: "Causes intense itching, red inflamed skin, dryness, and skin thickening. Can lead to secondary bacterial infections, sleep disturbance, and significant impact on quality of life.",
                etalons: {
                    primaryOrgan: ["Epidermis", "Dermis", "Sebaceous glands", "Hair follicles", "Skin barrier"],
                    pathomorphology: ["Barrier dysfunction", "Inflammatory infiltrate", "Hyperkeratosis", "Spongiosis"],
                    associatedSystems: ["Immune system", "Allergic response system", "Nervous system"],
                    biochemical: ["IgE", "Histamine", "Inflammatory cytokines", "Ceramides", "Filaggrin"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in skin barrier etalons indicate chronic dysfunction. Red triangles suggest acute flares. Black squares indicate severe skin compromise.",
                    graphNumbers: "Numbers 4-5 in barrier function etalons indicate dysfunction. Numbers 5-6 in inflammatory etalons suggest active eczema.",
                    anabolismCatabolism: "Red catabolism in inflamed skin areas. Blue anabolism compromised in barrier repair mechanisms.",
                    isoline: "Mild eczema range 0.3-0.5, moderate eczema 0.5-0.7, severe eczema 0.7-0.85",
                    kccValues: "KCC < 0.4 for inflammatory skin etalons indicates active eczema. Healthy skin etalons show KCC > 0.8",
                    entropyAnalysis: "E values 4-5 in pathomorphology etalons indicate established skin changes",
                    biochemicalHomeostasis: "E values 1 or 7 in allergic and inflammatory etalons indicate significant immune activation",
                    vegetativeTest: "+12% or more strengthening with skin-healing and anti-inflammatory preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete skin assessment with focus on barrier function and inflammatory patterns",
                    focusedAnalysis: "Detailed analysis of skin barrier integrity, allergic triggers, and inflammatory response patterns",
                    metaTherapy: {
                        selection: "Select skin inflammation etalons with highest activity (lowest KCC values)",
                        settings: "Level 2-3, Therapy mode, 15-20 minutes per session",
                        sessions: "2-3 sessions per week, monitor skin condition and itching",
                        focus: "Maximum 3-4 skin etalons per session"
                    },
                    vegetativeTest: "Test energetic compatibility with skin-healing, anti-inflammatory, and barrier-repair preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 4-6 weeks per cycle"
                },
                steps: [
                    "Skin barrier function assessment",
                    "Analysis of inflammatory and allergic responses",
                    "Meta-therapy on skin inflammation etalons",
                    "Vegetative testing of skin healing preparations",
                    "Skin condition evaluation"
                ],
                targets: ["Epidermis", "Dermis", "Sebaceous glands", "Immune cells"],
                notes: [
                    "CRITICAL: Identify and avoid environmental and food triggers",
                    "Moisturization absolutely crucial - apply multiple times daily",
                    "Use only gentle, fragrance-free skincare products",
                    "Stress management important for flare prevention"
                ]
            }
        ];

        // Initialize the application
        let filteredConditions = [...medicalConditions];

        function updateTotalCount() {
            document.getElementById('totalCount').textContent = medicalConditions.length;
        }

        function updateResultCount() {
            document.getElementById('resultCount').textContent = filteredConditions.length;
        }

        function createConditionCard(condition) {
            const categoryColors = {
                cardiovascular: 'bg-red-100 text-red-800',
                respiratory: 'bg-blue-100 text-blue-800',
                digestive: 'bg-green-100 text-green-800',
                neurological: 'bg-purple-100 text-purple-800',
                endocrine: 'bg-yellow-100 text-yellow-800',
                renal: 'bg-indigo-100 text-indigo-800',
                musculoskeletal: 'bg-orange-100 text-orange-800',
                dermatology: 'bg-pink-100 text-pink-800',
                detoxification: 'bg-teal-100 text-teal-800',
                parasites: 'bg-red-200 text-red-900',
                sports: 'bg-emerald-100 text-emerald-800',
                mental: 'bg-violet-100 text-violet-800',
                womens: 'bg-rose-100 text-rose-800',
                mens: 'bg-cyan-100 text-cyan-800',
                pediatric: 'bg-amber-100 text-amber-800',
                geriatric: 'bg-slate-100 text-slate-800'
            };

            return `
                <div class="condition-card bg-white rounded-lg shadow-md p-6 border border-gray-200" 
                     onclick="openModal('${condition.name}')">
                    <div class="flex items-start justify-between mb-3">
                        <h3 class="text-lg font-semibold text-gray-800 leading-tight">${condition.name}</h3>
                        <span class="px-2 py-1 text-xs font-medium rounded-full ${categoryColors[condition.category] || 'bg-gray-100 text-gray-800'}">
                            ${condition.category}
                        </span>
                    </div>
                    <div class="mb-3">
                        <p class="text-sm text-gray-600 mb-2">Body Systems:</p>
                        <div class="flex flex-wrap gap-1">
                            ${condition.systems.map(system => 
                                `<span class="px-2 py-1 bg-gray-100 text-gray-700 text-xs rounded">${system}</span>`
                            ).join('')}
                        </div>
                    </div>
                    <div class="mb-3">
                        <p class="text-sm text-gray-600 mb-1">Treatment Steps:</p>
                        <p class="text-xs text-gray-500">${condition.steps.length} protocol steps</p>
                    </div>
                    <div class="text-right">
                        <button class="text-blue-600 hover:text-blue-800 text-sm font-medium">
                            View Details →
                        </button>
                    </div>
                </div>
            `;
        }

        function renderConditions() {
            const grid = document.getElementById('conditionsGrid');
            if (filteredConditions.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full text-center py-12">
                        <div class="text-6xl mb-4">🔍</div>
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">No conditions found</h3>
                        <p class="text-gray-600">Try adjusting your search terms or filters</p>
                    </div>
                `;
            } else {
                grid.innerHTML = filteredConditions.map(createConditionCard).join('');
            }
            updateResultCount();
        }

        function filterConditions() {
            const searchTerm = document.getElementById('searchInput').value.toLowerCase();
            const systemFilter = document.getElementById('systemFilter').value;

            filteredConditions = medicalConditions.filter(condition => {
                const matchesSearch = condition.name.toLowerCase().includes(searchTerm) ||
                                    condition.systems.some(system => system.toLowerCase().includes(searchTerm)) ||
                                    condition.targets.some(target => target.toLowerCase().includes(searchTerm));
                
                const matchesSystem = !systemFilter || condition.category === systemFilter;

                return matchesSearch && matchesSystem;
            });

            renderConditions();
        }

        function openModal(conditionName) {
            const condition = medicalConditions.find(c => c.name === conditionName);
            if (!condition) return;

            document.getElementById('modalTitle').textContent = condition.name;
            document.getElementById('modalContent').innerHTML = `
                <div class="space-y-6">
                    ${condition.whatItIs ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">📋 What It Is</h3>
                        <p class="text-gray-700 bg-blue-50 p-4 rounded-lg">${condition.whatItIs}</p>
                    </div>
                    ` : ''}

                    ${condition.howItAffects ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">⚠️ How It Affects the Body</h3>
                        <p class="text-gray-700 bg-red-50 p-4 rounded-lg">${condition.howItAffects}</p>
                    </div>
                    ` : ''}

                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">🎯 Body Systems Involved</h3>
                        <div class="flex flex-wrap gap-2">
                            ${condition.systems.map(system => 
                                `<span class="px-3 py-1 bg-blue-100 text-blue-800 rounded-full text-sm">${system}</span>`
                            ).join('')}
                        </div>
                    </div>

                    ${condition.etalons ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">🔬 Etalons to Test</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="bg-green-50 p-4 rounded-lg">
                                <h4 class="font-medium text-green-800 mb-2">Primary Organs</h4>
                                <div class="space-y-1">
                                    ${condition.etalons.primaryOrgan.map(organ => 
                                        `<div class="text-sm text-green-700">• ${organ}</div>`
                                    ).join('')}
                                </div>
                            </div>
                            <div class="bg-purple-50 p-4 rounded-lg">
                                <h4 class="font-medium text-purple-800 mb-2">Pathomorphology</h4>
                                <div class="space-y-1">
                                    ${condition.etalons.pathomorphology.map(path => 
                                        `<div class="text-sm text-purple-700">• ${path}</div>`
                                    ).join('')}
                                </div>
                            </div>
                            <div class="bg-orange-50 p-4 rounded-lg">
                                <h4 class="font-medium text-orange-800 mb-2">Associated Systems</h4>
                                <div class="space-y-1">
                                    ${condition.etalons.associatedSystems.map(system => 
                                        `<div class="text-sm text-orange-700">• ${system}</div>`
                                    ).join('')}
                                </div>
                            </div>
                            <div class="bg-teal-50 p-4 rounded-lg">
                                <h4 class="font-medium text-teal-800 mb-2">Biochemical</h4>
                                <div class="space-y-1">
                                    ${condition.etalons.biochemical.map(bio => 
                                        `<div class="text-sm text-teal-700">• ${bio}</div>`
                                    ).join('')}
                                </div>
                            </div>
                        </div>
                    </div>
                    ` : ''}

                    ${condition.energeticMarkers ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">⚡ Energetic Markers (NLS Analysis)</h3>
                        <div class="space-y-4">
                            <div class="bg-yellow-50 p-4 rounded-lg">
                                <h4 class="font-medium text-yellow-800 mb-2">Flendler's Scale Icons</h4>
                                <p class="text-sm text-yellow-700">${condition.energeticMarkers.flendlerScale}</p>
                            </div>
                            <div class="bg-indigo-50 p-4 rounded-lg">
                                <h4 class="font-medium text-indigo-800 mb-2">Graph Interpretation</h4>
                                <p class="text-sm text-indigo-700 mb-2"><strong>Numbers:</strong> ${condition.energeticMarkers.graphNumbers}</p>
                                <p class="text-sm text-indigo-700 mb-2"><strong>Anabolism/Catabolism:</strong> ${condition.energeticMarkers.anabolismCatabolism}</p>
                                <p class="text-sm text-indigo-700"><strong>Isoline:</strong> ${condition.energeticMarkers.isoline}</p>
                            </div>
                            <div class="bg-gray-50 p-4 rounded-lg">
                                <h4 class="font-medium text-gray-800 mb-2">KCC & Entropy Values</h4>
                                <p class="text-sm text-gray-700 mb-2"><strong>KCC Values:</strong> ${condition.energeticMarkers.kccValues}</p>
                                <p class="text-sm text-gray-700 mb-2"><strong>Entropy Analysis:</strong> ${condition.energeticMarkers.entropyAnalysis}</p>
                                <p class="text-sm text-gray-700"><strong>Biochemical Homeostasis:</strong> ${condition.energeticMarkers.biochemicalHomeostasis}</p>
                            </div>
                        </div>
                    </div>
                    ` : ''}

                    ${condition.protocol ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">🔧 Energetic Protocol</h3>
                        <div class="space-y-4">
                            <div class="bg-blue-50 p-4 rounded-lg">
                                <h4 class="font-medium text-blue-800 mb-2">Initial Scan</h4>
                                <p class="text-sm text-blue-700">${condition.protocol.initialScan}</p>
                            </div>
                            <div class="bg-green-50 p-4 rounded-lg">
                                <h4 class="font-medium text-green-800 mb-2">Focused Analysis</h4>
                                <p class="text-sm text-green-700">${condition.protocol.focusedAnalysis}</p>
                            </div>
                            <div class="bg-purple-50 p-4 rounded-lg">
                                <h4 class="font-medium text-purple-800 mb-2">Meta-Therapy Settings</h4>
                                <p class="text-sm text-purple-700 mb-1"><strong>Selection:</strong> ${condition.protocol.metaTherapy.selection}</p>
                                <p class="text-sm text-purple-700 mb-1"><strong>Settings:</strong> ${condition.protocol.metaTherapy.settings}</p>
                                <p class="text-sm text-purple-700 mb-1"><strong>Sessions:</strong> ${condition.protocol.metaTherapy.sessions}</p>
                                <p class="text-sm text-purple-700"><strong>Focus:</strong> ${condition.protocol.metaTherapy.focus}</p>
                            </div>
                            <div class="bg-orange-50 p-4 rounded-lg">
                                <h4 class="font-medium text-orange-800 mb-2">Vegetative Test & Imprinting</h4>
                                <p class="text-sm text-orange-700 mb-2"><strong>Testing:</strong> ${condition.protocol.vegetativeTest}</p>
                                <p class="text-sm text-orange-700"><strong>Imprinting:</strong> ${condition.protocol.imprinting}</p>
                            </div>
                        </div>
                    </div>
                    ` : ''}

                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">📝 Treatment Protocol Steps</h3>
                        <div class="space-y-3">
                            ${condition.steps.map((step, index) => `
                                <div class="flex items-start space-x-3 p-3 bg-blue-50 rounded-lg">
                                    <div class="flex-shrink-0 w-6 h-6 bg-blue-600 text-white rounded-full flex items-center justify-center text-sm font-medium">
                                        ${index + 1}
                                    </div>
                                    <p class="text-gray-700">${step}</p>
                                </div>
                            `).join('')}
                        </div>
                    </div>

                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">🎯 Target Areas</h3>
                        <div class="grid grid-cols-2 md:grid-cols-3 gap-2">
                            ${condition.targets.map(target => 
                                `<div class="px-3 py-2 bg-green-100 text-green-800 rounded text-sm text-center">${target}</div>`
                            ).join('')}
                        </div>
                    </div>

                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">⚠️ Important Notes & Medical Disclaimer</h3>
                        <ul class="space-y-2">
                            ${condition.notes.map(note => 
                                `<li class="flex items-start space-x-2">
                                    <span class="text-red-500 mt-1">•</span>
                                    <span class="text-gray-700 ${note.includes('CRITICAL') ? 'font-semibold text-red-700' : ''}">${note}</span>
                                </li>`
                            ).join('')}
                        </ul>
                    </div>
                </div>
            `;
            document.getElementById('conditionModal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('conditionModal').classList.add('hidden');
        }

        // Event listeners
        document.getElementById('searchInput').addEventListener('input', filterConditions);
        document.getElementById('systemFilter').addEventListener('change', filterConditions);
        document.getElementById('closeModal').addEventListener('click', closeModal);

        // Close modal when clicking outside
        document.getElementById('conditionModal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeModal();
            }
        });

        // Initialize the application
        updateTotalCount();
        renderConditions();
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'97285a9152be8a59',t:'MTc1NTc2MDY3OS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
