# bioplasmanls
"A database of Bioplasm NLS V6 protocols for professional use."
medical database “mini‑app” that follows your exact Bioplasm NLS V6 structure (Title/Overview → Etalons → NLS markers → Protocol → Follow‑up → Systems/cells → Notes).

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Bioplasm NLS V6 – Complete Protocol Database</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    body{font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Arial}
    .card{box-shadow:0 10px 25px rgba(0,0,0,.08)}
    details>summary::-webkit-details-marker{display:none}
    .chip{border:1px solid #e5e7eb;border-radius:9999px;padding:.15rem .55rem;font-size:.75rem}
    .cat{border-left:4px solid #e5e7eb}
    .cat[data-cat="Cardiovascular"]{border-left-color:#dc2626}
    .cat[data-cat="Respiratory & ENT"]{border-left-color:#2563eb}
    .cat[data-cat="Digestive"]{border-left-color:#059669}
    .cat[data-cat="Neurology & CNS"]{border-left-color:#7c3aed}
    .cat[data-cat="Endocrine"]{border-left-color:#ea580c}
    .cat[data-cat="Renal & Urinary"]{border-left-color:#0891b2}
    .cat[data-cat="Musculoskeletal"]{border-left-color:#65a30d}
    .cat[data-cat="Dermatology"]{border-left-color:#e11d48}
    .cat[data-cat="Reproductive"]{border-left-color:#be185d}
    .cat[data-cat="Hematology"]{border-left-color:#b91c1c}
    .cat[data-cat="Infectious"]{border-left-color:#f59e0b}
    .cat[data-cat="Ophthalmology"]{border-left-color:#06b6d4}
    .cat[data-cat="Pediatric"]{border-left-color:#f472b6}
    .cat[data-cat="Chakra & Aura"]{border-left-color:#f59e0b}
    .kbd{border:1px solid #e5e7eb;border-bottom-width:2px;padding:.15rem .4rem;border-radius:.375rem;background:#fff}
    .sticky-top{position:sticky;top:0;z-index:30;background:white}
    .mono{font-family:ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,"Liberation Mono","Courier New",monospace}
  </style>
</head>
<body class="bg-gray-50">
  <!-- Header -->
  <header class="sticky-top border-b">
    <div class="max-w-7xl mx-auto px-4 py-4 flex items-center gap-3">
      <div class="text-white rounded-xl px-3 py-1 text-sm" style="background:linear-gradient(135deg,#1e3a8a,#7c3aed)">Bioplasm NLS V6</div>
      <h1 class="text-xl font-bold">Complete Protocol Database</h1>
      <div class="ml-auto flex gap-2">
        <button id="btnExport" class="px-3 py-1.5 rounded-md border bg-white hover:bg-gray-50">Export JSON</button>
        <label class="px-3 py-1.5 rounded-md border bg-white hover:bg-gray-50 cursor-pointer">
          Import JSON <input id="fileImport" type="file" accept="application/json" class="hidden">
        </label>
        <button id="btnPrint" class="px-3 py-1.5 rounded-md border bg-white hover:bg-gray-50">Print/Save</button>
      </div>
    </div>
  </header>

  <!-- Tools -->
  <section class="max-w-7xl mx-auto p-4">
    <div class="grid lg:grid-cols-4 gap-4">
      <div class="lg:col-span-1 card bg-white rounded-xl p-4">
        <h2 class="font-semibold mb-3">Filters</h2>
        <input id="q" type="search" placeholder="Search condition / etalon…" class="w-full border rounded-md px-3 py-2 mb-3" />
        <div id="catList" class="space-y-2"></div>
        <div class="mt-4 text-xs text-gray-500">Tip: Press <span class="kbd">/</span> to focus search.</div>
      </div>

      <div class="lg:col-span-3 space-y-4" id="results"></div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="border-t">
    <div class="max-w-7xl mx-auto px-4 py-6 text-xs text-gray-500">
      ⚠️ <b>Medical disclaimer:</b> Bioplasm/NLS work is complementary and does not diagnose, treat, or replace medical care. Always refer clients to licensed clinicians for diagnosis and treatment; use NLS only as an energetic support and monitoring tool.
    </div>
  </footer>

<script>
/** ========= DATA MODEL =========
Each item follows your required structure.
Copy this array out with “Export JSON”, edit in a text editor/Excel-to-JSON, then “Import JSON”.
**/
let DB = [
  {
    id:"cv-hypertension",
    category:"Cardiovascular",
    title:"Energetic Protocol: Hypertension",
    overview:{
      whatItIs:"Chronic elevation of arterial blood pressure; multifactorial (essential vs secondary).",
      howAffects:"Headache, dizziness, target-organ load (heart, kidneys, brain). Long-term risks: MI, stroke, CKD."
    },
    systems:["Cardiovascular System","Renal & Urinary System","Neurology & CNS","Endocrine System"],
    etalons:{
      "Primary Organ":[
        "Arterial walls","Endothelium","Smooth muscle of vessels","Heart (myocardium)","SA/AV nodes"
      ],
      "Pathomorphology":[
        "Atherosclerosis","Arterial stiffness","Microangiopathy"
      ],
      "Associated Systems":[
        "Kidneys (renal arteries, juxtaglomerular apparatus)","Adrenals (aldosterone/cortisol)","Thyroid"
      ],
      "Biochemical":[
        "Renin-angiotensin-aldosterone (RAAS)","Nitric oxide","Electrolytes (Na/K/Mg)","Oxidative stress"
      ]
    },
    markers:{
      icons:"↑ brown diamonds / red triangles on arteries indicate active strain; black squares = degenerative risk.",
      graph:"Deviation numbers 4–5 common. Red (catabolism) may dominate during spikes; blue (anabolism) low in chronic cases.",
      isoline:"Acute spike often above isoline; long-standing HTN hovers close but persistent.",
      kcc:"High KCC to HTN/arterial stiffness etalons; <0.425 to healthy artery is concerning.",
      entropy:"E=4–6 on pathomorphology suggests maturing vascular remodeling.",
      biochemicalE:"E=1 or 7 on RAAS/electrolytes indicates significant dysregulation.",
      vegeto:"+10% or more improvement with vascular tone remedies = positive."
    },
    protocol:{
      initialScan:[
        "Calibration → Adjust all",
        "Test → Absolute model (Heart, vessels, kidneys, adrenals, thyroid)",
        "Entropy Analysis → arterial wall, RAAS"
      ],
      focused:[
        "Object → Etalon groups above; review KCC & E values",
        "Comparative analysis baseline"
      ],
      metaTherapy:{
        selection:"Pick etalons showing highest stress (arterial wall, endothelium, RAAS).",
        settings:"Level 2–3, 70–80%, 7–10 min total split across 3–5 targets.",
        sessions:"1–2 rounds/session; observe post curves and compensatory rise.",
        focus:"Max 5 etalons per sitting."
      },
      vegetoImprint:{
        test:"Vegeto Test vasodilators, magnesium, adaptogens.",
        imprint:"Imprint best remedy to water/sugar pellets 30–60 sec; take 2–3× daily."
      },
      client:"Check BP pre/post; hydration; medical co‑management."
    },
    cellsTissues:{
      "Cardiovascular":["Myocardium","Coronary arteries","Aorta/peripheral arteries","Valves: Mitral, Aortic, Tricuspid, Pulmonary","SA node"],
      "Renal & Urinary":["Renal arteries","Glomeruli","Tubules","JGA (renin)"],
      "Endocrine":["Adrenal cortex (aldosterone, cortisol)","Thyroid"],
      "Neurology & CNS":["Autonomic centers (vasomotor), stress circuits"]
    },
    notes:[
      "Consider adrenal support in stress‑driven cases.",
      "Avoid long MT blocks in frail clients; short, frequent better."
    ]
  },

  {
    id:"gi-gerd",
    category:"Digestive",
    title:"Energetic Protocol: GERD",
    overview:{
      whatItIs:"Reflux of gastric contents into esophagus; functional LES weakness ± hiatal issues.",
      howAffects:"Heartburn, regurgitation, cough; risks: esophagitis, Barrett’s."
    },
    systems:["Digestive System","Autonomic/Stress","Respiratory (secondary)"],
    etalons:{
      "Primary Organ":["Esophagus mucosa","Lower esophageal sphincter (LES)","Stomach acid regulation"],
      "Pathomorphology":["Esophagitis grades","Barrett metaplasia"],
      "Associated Systems":["Vagus nerve tone","Diaphragmatic hiatus"],
      "Biochemical":["Acid/pepsin balance","Bile reflux markers"]
    },
    markers:{
      icons:"Red triangles on LES/mucosa during flares.",
      graph:"4–5 deviation typical; red line > blue in acute.",
      isoline:"Above isoline during active reflux.",
      kcc:"High KCC to esophagitis/hiatal etalons.",
      entropy:"E=4–6 on mucosa indicates ongoing irritation.",
      biochemicalE:"E=1/7 for acid/bile when out of range.",
      vegeto:"+10% with mucosa‑soothing or prokinetic remedies = good."
    },
    protocol:{
      initialScan:["Calibration","Test → Absolute (esophagus/stomach)","Entropy → mucosa/LES"],
      focused:["Object → Etalons; check H. pylori if dyspeptic","Comparative baseline"],
      metaTherapy:{selection:"Mucosa + LES tone",settings:"70–80% for 7–10 min",sessions:"1 round/session",focus:"≤4 etalons"},
      vegetoImprint:{test:"Mucosa soothers, prokinetics",imprint:"Imprint best remedy 30–60 sec → water"},
      client:"Avoid sessions during GI bleed. Diet triggers review."
    },
    cellsTissues:{
      "Digestive":["Esophageal epithelium","Gastric parietal cells","Diaphragm fibers"],
      "Autonomic":["Vagus nerve"]
    },
    notes:["Check coffee/citrus/gluten allergens; add breathing for diaphragm."]
  },

  {
    id:"hep-cirrhosis",
    category:"Digestive",
    title:"Energetic Protocol: Liver Cirrhosis (supportive)",
    overview:{
      whatItIs:"Chronic hepatic fibrosis with nodular remodeling; causes include viral hepatitis, alcohol, NASH.",
      howAffects:"Portal HTN, ascites, coagulopathy, encephalopathy."
    },
    systems:["Digestive","Cardiovascular (portal)","Immune","Hematology"],
    etalons:{
      "Primary Organ":["Hepatocytes","Fibrous septa","Portal vein"],
      "Pathomorphology":["Fibrosis stage","Ascites","Varices"],
      "Associated Systems":["Gut microbiome (endotoxins)","Biliary tree"],
      "Biochemical":["Bilirubin","Albumin","INR","Ammonia"]
    },
    markers:{
      icons:"Brown/black markers over liver lobules in advanced cases.",
      graph:"Chronic 4–5 deviation; low blue line.",
      isoline:"Near isoline but persistent.",
      kcc:"High to fibrosis; low to healthy parenchyma.",
      entropy:"E=5–6 on fibrosis = mature process.",
      biochemicalE:"E=1/7 on bilirubin/albumin/clotting → decomp.",
      vegeto:"+10% with drainage/antioxidants only as support."
    },
    protocol:{
      initialScan:["Calibration","Test → Absolute (liver/portal)","Entropy → fibrosis"],
      focused:["Object → Viral hepatitis, alcohol, microbiome","Comparative baseline"],
      metaTherapy:{selection:"Hepatocytes, microcirculation, drainage",settings:"70–75% 7–10 min",sessions:"Supportive only",focus:"≤4 etalons"},
      vegetoImprint:{test:"Silymarin, NAC, drainage",imprint:"30–60 sec → water"},
      client:"Mandatory hepatology care; MT is adjunct."
    },
    cellsTissues:{
      "Digestive":["Hepatocytes","Sinusoids","Kupffer cells","Bile canaliculi"],
      "Cardiovascular":["Portal vein","Collateral circulation"]
    },
    notes:["Avoid MT in fulminant hepatitis; monitor encephalopathy signs."]
  },

  {
    id:"endo-diabetes2",
    category:"Endocrine",
    title:"Energetic Protocol: Type 2 Diabetes (supportive)",
    overview:{
      whatItIs:"Metabolic disorder with insulin resistance ± beta‑cell dysfunction.",
      howAffects:"Hyperglycemia, vascular damage, neuropathy, nephropathy."
    },
    systems:["Endocrine","Cardiovascular","Neurology & CNS","Renal & Urinary"],
    etalons:{
      "Primary Organ":["Pancreatic islets (β‑cells)","Liver (gluconeogenesis)","Adipocytes"],
      "Pathomorphology":["Glycation","Microangiopathy"],
      "Associated Systems":["Gut microbiome","Inflammation"],
      "Biochemical":["Insulin signaling","Glucose transporters","Lipid profile"]
    },
    markers:{
      icons:"Red triangles over pancreas/liver/adipose.",
      graph:"4–5 deviation on metabolic panels.",
      isoline:"Often chronic near‑isoline.",
      kcc:"High to insulin resistance etalons.",
      entropy:"E=4–6 on metabolic stress.",
      biochemicalE:"E=1 or 7 on glucose/lipids.",
      vegeto:"+10% with insulin‑sensitizing remedies."
    },
    protocol:{
      initialScan:["Calibration","Test → Absolute (pancreas/liver/adipose)","Entropy → β‑cells"],
      focused:["Object → insulin signaling, inflammation","Comparative baseline"],
      metaTherapy:{selection:"β‑cells, liver metabolism",settings:"70–80% 7–10 min",sessions:"1–2 rounds",focus:"≤5 etalons"},
      vegetoImprint:{test:"Berberine, cinnamon, chromium",imprint:"30–60 sec → water"},
      client:"Coordinate with medical glycemic management."
    },
    cellsTissues:{
      "Endocrine":["β‑cells","Adipocytes","Mitochondria"],
      "Cardiovascular":["Capillaries"],
      "Neurology":["Peripheral nerves (neuropathy)"],
      "Renal":["Glomeruli"]
    },
    notes:["Check dysbiosis; hydration; foot/eye screening advised."]
  },

  {
    id:"neuro-bipolar",
    category:"Neurology & CNS",
    title:"Energetic Protocol: Bipolar Disorder (supportive)",
    overview:{
      whatItIs:"Mood disorder with manic/hypomanic and depressive episodes.",
      howAffects:"Affects emotion regulation; relapse risk without medical care."
    },
    systems:["Neurology & CNS","Endocrine","Chakra & Aura"],
    etalons:{
      "Primary Organ":["Prefrontal cortex","Limbic system","Basal ganglia"],
      "Associated Systems":["Thyroid","Adrenals","Pineal"],
      "Biochemical":["Dopamine","Serotonin","GABA","Cortisol rhythm"]
    },
    markers:{
      icons:"Stress icons over limbic + prefrontal.",
      graph:"Fluctuating 4–5 with catabolic surges in mania.",
      isoline:"Acute episodes above isoline.",
      kcc:"High to dopamine dysregulation.",
      entropy:"E=4–5 on stress circuits.",
      biochemicalE:"E=1/7 on cortisol/thyroid if dysregulated.",
      vegeto:"+10% with stabilizing remedies."
    },
    protocol:{
      initialScan:["Calibration","Test → Absolute (brain + endocrine)","Entropy → limbic/prefrontal"],
      focused:["Object → neurotransmitters, stress axis","Comparative baseline"],
      metaTherapy:{selection:"Frontal/limbic balancing",settings:"70–80% 8–12 min",sessions:"Short, repeated blocks",focus:"≤4 targets"},
      vegetoImprint:{test:"Omega‑3, Mg, adaptogens",imprint:"30–60 sec → water"},
      client:"Adjunct only; maintain psychiatric care."
    },
    cellsTissues:{
      "Neurology":["Neurons","Synapses","Myelin"],
      "Endocrine":["Thyroid","Adrenal","Pineal"]
    },
    notes:["Aura scan often shows Third‑eye/Solar plexus imbalance; rebalance after MT."]
  },

  {
    id:"neuro-schizophrenia",
    category:"Neurology & CNS",
    title:"Energetic Protocol: Schizophrenia (supportive)",
    overview:{
      whatItIs:"Chronic psychotic-spectrum disorder; dysregulated dopamine/glutamate signaling.",
      howAffects:"Perception/thought disturbances; high relapse risk without medical therapy."
    },
    systems:["Neurology & CNS","Endocrine","Immune"],
    etalons:{
      "Primary Organ":["Frontal/temporal lobes","Hippocampus","Thalamus"],
      "Associated Systems":["Pineal/adrenal","Microglia activation"],
      "Biochemical":["Dopamine excess","Glutamate receptors"]
    },
    markers:{
      icons:"Markers over temporal/frontal circuits.",
      graph:"4–5 deviations; catabolic spikes during agitation.",
      isoline:"Often above during acute episodes.",
      kcc:"High to dopamine/glutamate pathology.",
      entropy:"E=4–6 on stress/inflammation.",
      biochemicalE:"E extremes on neurotransmitter panels.",
      vegeto:"+10% with calming antioxidants/adaptogens."
    },
    protocol:{
      initialScan:["Calibration","Test → Absolute (brain/immune/endocrine)","Entropy → temporal/frontal"],
      focused:["Object → dopamine/glutamate/microglia","Comparative baseline"],
      metaTherapy:{selection:"Frontal–limbic stabilization",settings:"70–80% 10–15 min",sessions:"Gentle, consistent",focus:"≤4 targets"},
      vegetoImprint:{test:"B vitamins, NAC, glycine",imprint:"30–60 sec → water"},
      client:"Strictly adjunct; coordinate with psychiatry."
    },
    cellsTissues:{
      "Neurology":["Cortical neurons","Hippocampal circuits","Myelin"],
      "Immune":["Microglia"]
    },
    notes:["Aura/Crown/Third‑eye balancing may help integration."]
  },

  {
    id:"ent-tinnitus",
    category:"Respiratory & ENT",
    title:"Energetic Protocol: Tinnitus (supportive)",
    overview:{
      whatItIs:"Perception of ringing without external sound; cochlear/nerve/vascular origins.",
      howAffects:"Sleep/anxiety burden; may be unilateral or bilateral
