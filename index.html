<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no"/>
  <meta name="theme-color" content="#0A0A0A"/>
  <meta name="apple-mobile-web-app-capable" content="yes"/>
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent"/>
  <meta name="apple-mobile-web-app-title" content="Jackedlete"/>
  <title>Jackedlete</title>
  <style>body{margin:0;background:#0A0A0A;}</style>
  <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
</head>
<body>
<div id="root"></div>
<script type="text/babel">
const { useState, useEffect, useRef, useCallback } = React;

// ─── PHASES ───────────────────────────────────────────────────────────────────
const PHASES = [
  {
    id: 1,
    name: "FOUNDATION",
    sub: "Cardiac Rehab · Movement Re-Patterning",
    color: "#E87B6E",
    weeks: "Months 1–2",
    hrCeiling: 120,
    rpe: 6,
    description: "Rebuild the foundation. Establish movement patterns, let the heart heal, and restore confidence under load. DBs and machines only. No Valsalva. No ego.",
    cardioTarget: "30–35 min Zone 2 · HR 100–115",
    criteria: [
      "No chest pain, dizziness, or unusual SOB during training",
      "HR returning below 100 BPM within 5 min post-set",
      "Completed 6+ weeks of consistent training",
      "Cardiologist cleared for increased intensity",
    ],
    unlocks: ["Dumbbell movements only", "Machine compounds", "Bodyweight progressions", "Zone 2 cardio only"],
  },
  {
    id: 2,
    name: "BUILD",
    sub: "Hypertrophy Volume · Moderate Intensity",
    color: "#C9A84C",
    weeks: "Months 3–4",
    hrCeiling: 130,
    rpe: 7,
    description: "Volume accumulation. CBum-style tempo work, wave loading, and superset architecture. Hypertrophy is the primary driver. Cardiac parameters expand but remain respected.",
    cardioTarget: "35–45 min Zone 2 · HR 105–125",
    criteria: [
      "HR ceiling can be raised to 140 BPM per cardiologist",
      "No cardiac events or symptoms in Phase 2",
      "8+ weeks of consistent Phase 2 training",
      "Cardiologist cleared for barbell movements",
    ],
    unlocks: ["Full machine compound suite", "Higher rep ranges", "Superset architecture", "Cardio volume increase"],
  },
  {
    id: 3,
    name: "STRENGTHEN",
    sub: "Barbell Reintroduction · Running Intervals",
    color: "#7EB8D4",
    weeks: "Months 5–6",
    hrCeiling: 140,
    rpe: 8,
    description: "Barbell movements return. Squat, deadlift, and bench reintroduced with controlled progression. Running intervals begin. Strength and athleticism rebuild in parallel.",
    cardioTarget: "40–50 min · Zone 2 + 3 intervals · HR up to 140",
    criteria: [
      "6+ months post-surgery with full cardiologist clearance",
      "No symptoms during Phase 3 training",
      "HR recovery under 2 min post-set",
      "Cleared for high-intensity interval training",
    ],
    unlocks: ["Barbell squat and deadlift", "Barbell bench press", "Running intervals", "Heavier loading ranges"],
  },
  {
    id: 4,
    name: "ATHLETIC",
    sub: "Full Program · Return to Run Protocol",
    color: "#58A45C",
    weeks: "Month 6+",
    hrCeiling: 155,
    rpe: 9,
    description: "The Jackedlete in full. Maximum hypertrophy stimulus, athletic conditioning, and progressive running protocol. Built to last decades. This is where you live.",
    cardioTarget: "Full Zone 2–4 training · Structured run program",
    criteria: [],
    unlocks: ["Full barbell program", "Progressive run protocol", "High intensity intervals", "Competition prep capable"],
  },
];

// ─── REST CONFIG ──────────────────────────────────────────────────────────────
const REST_CONFIG = {
  "A SERIES":          { upper:120, lower:150, label_u:"2:00 REST", label_l:"2:30 REST", cardiac:"Heavy compound — full HR recovery before next set" },
  "B1/B2 SERIES":      { upper:90,  lower:90,  label_u:"1:30 REST", label_l:"1:30 REST", cardiac:"Superset — 90 sec minimum, monitor HR before proceeding" },
  "C1/C2 SERIES":      { upper:60,  lower:60,  label_u:"1:00 REST", label_l:"1:00 REST", cardiac:"Pump finisher — lighter load, shorter rest appropriate" },
  "MOVEMENT PREP":     { upper:45,  lower:45,  label_u:"0:45 REST", label_l:"0:45 REST", cardiac:"Mobility work — brief recovery" },
  "ZONE 2 CARDIO":     { upper:0,   lower:0,   label_u:"",          label_l:"",          cardiac:"" },
  "OPTIONAL FINISHER": { upper:60,  lower:60,  label_u:"1:00 REST", label_l:"1:00 REST", cardiac:"Loaded carry — moderate cardiac demand" },
  "BARBELL WORK":      { upper:150, lower:180, label_u:"2:30 REST", label_l:"3:00 REST", cardiac:"Heavy barbell — maximum HR recovery, no rushing" },
  "RUN INTERVALS":     { upper:120, lower:120, label_u:"2:00 REST", label_l:"2:00 REST", cardiac:"Running interval recovery — HR must drop below 120 before next" },
};
const LOWER_DAYS = ["PUSH A","PUSH B"];
function getRestInfo(sn, dl) {
  const cfg = REST_CONFIG[sn] || { upper:90, lower:90, label_u:"1:30 REST", label_l:"1:30 REST", cardiac:"" };
  const isL = LOWER_DAYS.includes(dl) && sn==="A SERIES";
  return { secs:isL?cfg.lower:cfg.upper, label:isL?cfg.label_l:cfg.label_u, cardiac:cfg.cardiac };
}

// ─── PROGRAM DATA BY PHASE ────────────────────────────────────────────────────
const PROGRAMS = {

  // ── PHASE 1 ─────────────────────────────────────────────────────────────────
  1: [
    {
      id:"p1d1",day:"01",label:"PUSH A",sub:"Chest · Quad · Tricep",color:"#E87B6E",
      series:[
        {id:"p1d1a",name:"A SERIES",type:"straight",exercises:[
          {id:"p1d1a1",name:"Leg Press — Two Feet",sets:4,repsScheme:["12","10","10","10"],tempo:"2/0/X/0",cue:"Feet mid-platform. Controlled descent. Monitor HR."},
        ]},
        {id:"p1d1b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p1d1b1",name:"Goblet Squat",sets:3,repsScheme:["12","12","12"],tempo:"3/1/X/0",cue:"Single DB. 1-sec pause in hole. Feel quad load."},
          {id:"p1d1b2",name:"Seated Leg Curl",sets:3,repsScheme:["12","12","12"],tempo:"3/0/1/0",cue:"Full hamstring stretch. Controlled lowering."},
        ]},
        {id:"p1d1c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p1d1c1",name:"DB Bench Press — Flat",sets:3,repsScheme:["12","12","12"],tempo:"3/0/X/0",cue:"Dumbbells only. Easier to bail safely. Full chest stretch."},
          {id:"p1d1c2",name:"Cable Tricep Pushdown",sets:3,repsScheme:["15","15","15"],tempo:"2/0/1/0",cue:"Light weight. Full extension. Squeeze at bottom."},
        ]},
      ],
    },
    {
      id:"p1d2",day:"02",label:"PULL A",sub:"Back · Hamstring · Bicep",color:"#E87B6E",
      series:[
        {id:"p1d2a",name:"A SERIES",type:"straight",exercises:[
          {id:"p1d2a1",name:"Lat Pulldown — Wide Grip",sets:4,repsScheme:["12","10","10","10"],tempo:"2/0/X/0",cue:"Full stretch at top. Drive elbows down and back."},
        ]},
        {id:"p1d2b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p1d2b1",name:"Seated Cable Row",sets:3,repsScheme:["12","12","12"],tempo:"2/1/X/0",cue:"1-sec pause at full stretch. Squeeze mid-back."},
          {id:"p1d2b2",name:"DB Lateral Raise",sets:3,repsScheme:["15","15","15"],tempo:"2/0/1/0",cue:"Light weight. Lead with elbow. 1-sec hold at peak."},
        ]},
        {id:"p1d2c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p1d2c1",name:"DB Hammer Curl",sets:3,repsScheme:["12","12","12"],tempo:"2/0/1/1",cue:"Neutral grip. 1-sec squeeze at top. No swing."},
          {id:"p1d2c2",name:"Face Pull",sets:3,repsScheme:["15","15","15"],tempo:"2/0/1/1",cue:"Elbows high. Pull to ears. Rotator cuff health."},
        ]},
      ],
    },
    {
      id:"p1d3",day:"03",label:"ATHLETIC",sub:"Remedial Movement · Zone 2",color:"#58A45C",
      series:[
        {id:"p1d3a",name:"MOVEMENT PREP",type:"straight",exercises:[
          {id:"p1d3a1",name:"Hip 90/90 Stretch",sets:3,repsScheme:["60s","60s","60s"],tempo:"—",cue:"Each side. Hip internal/external rotation."},
          {id:"p1d3a2",name:"Thoracic Rotation",sets:3,repsScheme:["10","10","10"],tempo:"—",cue:"Quadruped. Each side. Open toward ceiling."},
          {id:"p1d3a3",name:"Single Leg Balance",sets:3,repsScheme:["30s","30s","30s"],tempo:"—",cue:"Each leg. Eyes open first, then close when easy."},
          {id:"p1d3a4",name:"Lateral Band Walk",sets:3,repsScheme:["15","15","15"],tempo:"—",cue:"Each direction. Glute medius activation."},
          {id:"p1d3a5",name:"Dead Hang",sets:3,repsScheme:["20s","20s","20s"],tempo:"—",cue:"Shoulder decompression. Passive hang."},
        ]},
        {id:"p1d3b",name:"ZONE 2 CARDIO",type:"straight",exercises:[
          {id:"p1d3b1",name:"Stationary Bike / Easy Walk",sets:1,repsScheme:["30–35 min"],tempo:"—",cue:"HR 100–115 BPM. Conversational pace. This is medicine."},
        ]},
      ],
    },
    {
      id:"p1d4",day:"04",label:"PUSH B",sub:"Shoulder · Quad · Tricep",color:"#E87B6E",
      series:[
        {id:"p1d4a",name:"A SERIES",type:"straight",exercises:[
          {id:"p1d4a1",name:"Seated DB Shoulder Press",sets:4,repsScheme:["12","10","10","10"],tempo:"2/0/X/0",cue:"Seated = lower HR. Don't lock out at top."},
        ]},
        {id:"p1d4b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p1d4b1",name:"Walking Lunge — Bodyweight",sets:3,repsScheme:["10","10","10"],tempo:"2/0/X/0",cue:"Each leg. Upright torso. Controlled step."},
          {id:"p1d4b2",name:"Leg Extension",sets:3,repsScheme:["15","15","15"],tempo:"2/0/1/1",cue:"Lean forward. Squeeze at top 1 sec. Light weight."},
        ]},
        {id:"p1d4c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p1d4c1",name:"Cable Lateral Raise",sets:3,repsScheme:["15","15","15"],tempo:"2/0/1/0",cue:"Constant tension. Lead with elbow. Feel medial delt."},
          {id:"p1d4c2",name:"Overhead DB Tricep Extension",sets:3,repsScheme:["12","12","12"],tempo:"3/0/X/0",cue:"Long head stretch. Feel behind head. Controlled."},
        ]},
      ],
    },
    {
      id:"p1d5",day:"05",label:"PULL B",sub:"Back · Hip Hinge · Bicep",color:"#E87B6E",
      series:[
        {id:"p1d5a",name:"A SERIES",type:"straight",exercises:[
          {id:"p1d5a1",name:"Assisted Pull-Up or Band Pulldown",sets:4,repsScheme:["8","8","8","8"],tempo:"2/0/X/0",cue:"Full lat stretch at top. Drive elbows down."},
        ]},
        {id:"p1d5b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p1d5b1",name:"Romanian Deadlift — Dumbbell",sets:3,repsScheme:["12","12","12"],tempo:"3/1/X/0",cue:"Hip hinge. 1-sec pause at max hamstring stretch."},
          {id:"p1d5b2",name:"Seated Calf Raise",sets:3,repsScheme:["15","15","15"],tempo:"2/2/X/1",cue:"2-sec pause at bottom stretch. Explosive drive up."},
        ]},
        {id:"p1d5c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p1d5c1",name:"Incline DB Curl",sets:3,repsScheme:["12","12","12"],tempo:"3/0/1/0",cue:"45° incline. Long head stretch at bottom."},
          {id:"p1d5c2",name:"Cable Pushdown — Rope",sets:3,repsScheme:["15","15","15"],tempo:"2/0/1/0",cue:"Split rope at bottom. Squeeze lateral head."},
        ]},
      ],
    },
  ],

  // ── PHASE 2 ─────────────────────────────────────────────────────────────────
  2: [
    {
      id:"p2d1",day:"01",label:"PUSH A",sub:"Chest · Quad · Tricep",color:"#C9A84C",
      series:[
        {id:"p2d1a",name:"A SERIES",type:"straight",exercises:[
          {id:"p2d1a1",name:"Hack Squat — Medium Stance",sets:6,repsScheme:["8","6","8","6","6","8"],tempo:"2/0/X/0",cue:"Feet low/narrow. Quad stretch at bottom. Monitor HR."},
        ]},
        {id:"p2d1b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p2d1b1",name:"Front Foot Elevated DB Split Squat",sets:4,repsScheme:["6","10","10","10"],tempo:"3/1/X/0",cue:"1-sec pause in hole. Upright torso."},
          {id:"p2d1b2",name:"Single Leg Lying Leg Curl",sets:4,repsScheme:["6","7","7","7"],tempo:"4/1/X/1",cue:"4-sec eccentric. Squeeze 1 sec at top."},
        ]},
        {id:"p2d1c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p2d1c1",name:"Incline DB Press",sets:3,repsScheme:["10","10","10"],tempo:"3/0/X/0",cue:"Drive elbows together at top. 30–45° incline."},
          {id:"p2d1c2",name:"Cable Tricep Pushdown — Rope",sets:3,repsScheme:["12","12","12"],tempo:"2/0/1/1",cue:"Split rope at bottom. Squeeze 1 sec."},
        ]},
      ],
    },
    {
      id:"p2d2",day:"02",label:"PULL A",sub:"Back · Hamstring · Bicep",color:"#C9A84C",
      series:[
        {id:"p2d2a",name:"A SERIES",type:"straight",exercises:[
          {id:"p2d2a1",name:"Single Arm Supinated Lat Pulldown",sets:6,repsScheme:["8","6","8","6","6","8"],tempo:"2/0/X/0",cue:"Full stretch at top. Supination = lat-bicep tie-in."},
        ]},
        {id:"p2d2b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p2d2b1",name:"Neutral Chest Supported T-Bar Row",sets:4,repsScheme:["6","10","10","10"],tempo:"3/1/X/0",cue:"1-sec pause at full stretch. Drive elbows back hard."},
          {id:"p2d2b2",name:"Single Arm Standing DB Lateral Raise",sets:4,repsScheme:["6","15","15","15"],tempo:"2/0/1/0",cue:"Lead with elbow. 1-sec hold at peak. Zero swing."},
        ]},
        {id:"p2d2c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p2d2c1",name:"Bent Over Supported Supinated DB Curl",sets:4,repsScheme:["6","15","15","15"],tempo:"2/0/1/1",cue:"No momentum. 1-sec squeeze + hold at bottom."},
          {id:"p2d2c2",name:"Low Pulley Sideways D-Handle Cable Curl",sets:4,repsScheme:["6","10","10","10"],tempo:"3/0/1/0",cue:"Stand sideways to cable. Long head peak."},
        ]},
      ],
    },
    {
      id:"p2d3",day:"03",label:"ATHLETIC",sub:"Remedial Movement · Zone 2",color:"#58A45C",
      series:[
        {id:"p2d3a",name:"MOVEMENT PREP",type:"straight",exercises:[
          {id:"p2d3a1",name:"Hip 90/90 Stretch",sets:3,repsScheme:["60s","60s","60s"],tempo:"—",cue:"Each side. Hip internal/external rotation."},
          {id:"p2d3a2",name:"Thoracic Rotation (Quadruped)",sets:3,repsScheme:["10","10","10"],tempo:"—",cue:"Each side. Open toward ceiling."},
          {id:"p2d3a3",name:"Single Leg Balance Reach",sets:3,repsScheme:["10","10","10"],tempo:"—",cue:"Each leg. Reach opposite hand to floor."},
          {id:"p2d3a4",name:"Lateral Band Walk",sets:3,repsScheme:["15","15","15"],tempo:"—",cue:"Each direction. Glute medius activation."},
          {id:"p2d3a5",name:"Dead Hang",sets:3,repsScheme:["25s","25s","25s"],tempo:"—",cue:"Shoulder decompression. Passive hang."},
        ]},
        {id:"p2d3b",name:"ZONE 2 CARDIO",type:"straight",exercises:[
          {id:"p2d3b1",name:"Stationary Bike / Easy Walk",sets:1,repsScheme:["35–45 min"],tempo:"—",cue:"HR 105–125 BPM. Full conversational pace."},
        ]},
        {id:"p2d3c",name:"OPTIONAL FINISHER",type:"straight",exercises:[
          {id:"p2d3c1",name:"Farmer's Carry",sets:3,repsScheme:["40m","40m","40m"],tempo:"—",cue:"Moderate DBs. Grip, core, gait mechanics."},
        ]},
      ],
    },
    {
      id:"p2d4",day:"04",label:"PUSH B",sub:"Shoulder · Quad Variation · Tricep",color:"#C9A84C",
      series:[
        {id:"p2d4a",name:"A SERIES",type:"straight",exercises:[
          {id:"p2d4a1",name:"Seated DB Shoulder Press",sets:6,repsScheme:["8","6","8","6","6","8"],tempo:"2/0/X/0",cue:"Seated = lower HR. Don't lock out — keep delt tension."},
        ]},
        {id:"p2d4b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p2d4b1",name:"Cable Lateral Raise",sets:4,repsScheme:["6","15","15","15"],tempo:"2/0/1/0",cue:"Lean from cable. 1-sec hold at peak."},
          {id:"p2d4b2",name:"Rope Face Pull",sets:4,repsScheme:["6","15","15","15"],tempo:"2/0/1/1",cue:"Elbows high. Pull to ears. 1-sec squeeze."},
        ]},
        {id:"p2d4c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p2d4c1",name:"Goblet Squat",sets:3,repsScheme:["10","12","12"],tempo:"3/1/X/0",cue:"1-sec pause in hole. Feel VMO load."},
          {id:"p2d4c2",name:"Overhead Cable Tricep Extension",sets:3,repsScheme:["12","12","12"],tempo:"3/0/X/0",cue:"Face away. Feel long head stretch. 3-sec eccentric."},
        ]},
      ],
    },
    {
      id:"p2d5",day:"05",label:"PULL B",sub:"Back Width · Hip Hinge · Bicep",color:"#C9A84C",
      series:[
        {id:"p2d5a",name:"A SERIES",type:"straight",exercises:[
          {id:"p2d5a1",name:"Lat Pulldown — Wide Grip Overhand",sets:6,repsScheme:["8","6","8","6","6","8"],tempo:"2/0/X/0",cue:"Full stretch at top. Drive elbows down and back."},
        ]},
        {id:"p2d5b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p2d5b1",name:"Romanian Deadlift — Dumbbell",sets:4,repsScheme:["6","10","10","10"],tempo:"3/1/X/0",cue:"1-sec pause at max hamstring stretch. Push hips back."},
          {id:"p2d5b2",name:"Seated Calf Raise",sets:4,repsScheme:["6","15","15","15"],tempo:"2/2/X/1",cue:"2-sec pause at bottom stretch. Explosive drive."},
        ]},
        {id:"p2d5c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p2d5c1",name:"Incline DB Curl",sets:4,repsScheme:["6","12","12","12"],tempo:"3/0/1/1",cue:"45–60° incline. Long head stretch. No swing."},
          {id:"p2d5c2",name:"EZ Bar Skull Crusher",sets:4,repsScheme:["6","12","12","12"],tempo:"3/0/X/0",cue:"Drop bench to flat. Same bar. Lower to forehead slowly."},
        ]},
      ],
    },
  ],

  // ── PHASE 3 ─────────────────────────────────────────────────────────────────
  3: [
    {
      id:"p3d1",day:"01",label:"PUSH A",sub:"Barbell Squat · Chest · Tricep",color:"#7EB8D4",
      series:[
        {id:"p3d1a",name:"BARBELL WORK",type:"straight",exercises:[
          {id:"p3d1a1",name:"Barbell Back Squat",sets:5,repsScheme:["5","5","5","5","5"],tempo:"3/1/X/0",cue:"CONTROLLED Valsalva only. Brace, descend, drive. Build weight slowly over weeks."},
        ]},
        {id:"p3d1b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p3d1b1",name:"Hack Squat — Medium Stance",sets:3,repsScheme:["10","10","10"],tempo:"2/0/X/0",cue:"Follow barbell squat with machine volume. Quad pump."},
          {id:"p3d1b2",name:"Single Leg Lying Leg Curl",sets:3,repsScheme:["10","10","10"],tempo:"3/1/X/1",cue:"Full hamstring development. 1-sec squeeze at top."},
        ]},
        {id:"p3d1c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p3d1c1",name:"Barbell Bench Press",sets:4,repsScheme:["6","6","6","6"],tempo:"3/1/X/0",cue:"Controlled descent. 1-sec pause at chest. Drive."},
          {id:"p3d1c2",name:"Cable Tricep Pushdown — Rope",sets:4,repsScheme:["12","12","12","12"],tempo:"2/0/1/1",cue:"Split rope at bottom. Squeeze 1 sec."},
        ]},
      ],
    },
    {
      id:"p3d2",day:"02",label:"PULL A",sub:"Deadlift · Back · Bicep",color:"#7EB8D4",
      series:[
        {id:"p3d2a",name:"BARBELL WORK",type:"straight",exercises:[
          {id:"p3d2a1",name:"Barbell Romanian Deadlift",sets:4,repsScheme:["6","6","6","6"],tempo:"3/1/X/0",cue:"Hip hinge. 1-sec stretch pause. Build to conventional deadlift over 4 weeks."},
        ]},
        {id:"p3d2b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p3d2b1",name:"Weighted Pull-Up or Lat Pulldown",sets:4,repsScheme:["8","8","8","8"],tempo:"2/0/X/0",cue:"Add weight to pull-ups if bodyweight is easy."},
          {id:"p3d2b2",name:"Single Arm DB Row",sets:4,repsScheme:["10","10","10","10"],tempo:"3/1/X/0",cue:"Full ROM. 1-sec pause at top contraction."},
        ]},
        {id:"p3d2c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p3d2c1",name:"EZ Bar Curl",sets:4,repsScheme:["10","10","10","10"],tempo:"2/0/1/1",cue:"Supinate at top. 1-sec squeeze. 3-sec eccentric."},
          {id:"p3d2c2",name:"Face Pull",sets:3,repsScheme:["15","15","15"],tempo:"2/0/1/1",cue:"Elbows high. Rotator cuff integrity."},
        ]},
      ],
    },
    {
      id:"p3d3",day:"03",label:"ATHLETIC",sub:"Run Intervals · Movement Work",color:"#58A45C",
      series:[
        {id:"p3d3a",name:"MOVEMENT PREP",type:"straight",exercises:[
          {id:"p3d3a1",name:"Hip 90/90 + Thoracic Rotation",sets:2,repsScheme:["60s","60s"],tempo:"—",cue:"Combined mobility circuit. Each side."},
          {id:"p3d3a2",name:"Single Leg RDL — Bodyweight",sets:3,repsScheme:["8","8","8"],tempo:"—",cue:"Each leg. Balance and posterior chain."},
          {id:"p3d3a3",name:"Lateral Band Walk",sets:2,repsScheme:["20","20"],tempo:"—",cue:"Glute medius — running mechanics prep."},
        ]},
        {id:"p3d3b",name:"RUN INTERVALS",type:"straight",exercises:[
          {id:"p3d3b1",name:"Walk/Jog Intervals",sets:6,repsScheme:["2 min jog","2 min jog","2 min jog","2 min jog","2 min jog","2 min jog"],tempo:"—",cue:"2 min easy jog / 2 min walk. HR must drop below 120 in walk. Stop if chest pressure."},
        ]},
        {id:"p3d3c",name:"ZONE 2 CARDIO",type:"straight",exercises:[
          {id:"p3d3c1",name:"Easy Bike / Walk Cooldown",sets:1,repsScheme:["15–20 min"],tempo:"—",cue:"HR 100–115. Full cooldown after intervals."},
        ]},
      ],
    },
    {
      id:"p3d4",day:"04",label:"PUSH B",sub:"Overhead · Quad · Tricep",color:"#7EB8D4",
      series:[
        {id:"p3d4a",name:"BARBELL WORK",type:"straight",exercises:[
          {id:"p3d4a1",name:"Barbell Overhead Press",sets:4,repsScheme:["6","6","6","6"],tempo:"2/1/X/0",cue:"Standing or seated. Brace core. Drive bar overhead. Monitor HR."},
        ]},
        {id:"p3d4b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p3d4b1",name:"Front Foot Elevated Split Squat",sets:4,repsScheme:["8","8","8","8"],tempo:"3/1/X/0",cue:"Add weight from Phase 2. Deeper stretch."},
          {id:"p3d4b2",name:"Cable Lateral Raise",sets:4,repsScheme:["15","15","15","15"],tempo:"2/0/1/0",cue:"Constant tension. 1-sec hold at peak."},
        ]},
        {id:"p3d4c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p3d4c1",name:"Goblet Squat — Heavier",sets:3,repsScheme:["10","10","10"],tempo:"3/1/X/0",cue:"Increase weight from Phase 2. Same form."},
          {id:"p3d4c2",name:"Skull Crusher — EZ Bar",sets:3,repsScheme:["10","10","10"],tempo:"3/0/X/0",cue:"Long head priority. Slow eccentric."},
        ]},
      ],
    },
    {
      id:"p3d5",day:"05",label:"PULL B",sub:"Back Width · Hinge · Conditioning",color:"#7EB8D4",
      series:[
        {id:"p3d5a",name:"A SERIES",type:"straight",exercises:[
          {id:"p3d5a1",name:"Weighted Pull-Up",sets:5,repsScheme:["6","6","6","6","6"],tempo:"2/0/X/1",cue:"Add belt weight. Full ROM. 1-sec squeeze at top."},
        ]},
        {id:"p3d5b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p3d5b1",name:"Barbell RDL — Building to Conventional",sets:4,repsScheme:["8","8","8","8"],tempo:"3/1/X/0",cue:"Progress hip hinge pattern toward full deadlift."},
          {id:"p3d5b2",name:"Seated Calf Raise",sets:4,repsScheme:["15","15","15","15"],tempo:"2/2/X/1",cue:"2-sec stretch pause. Running prep."},
        ]},
        {id:"p3d5c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p3d5c1",name:"Incline DB Curl",sets:3,repsScheme:["10","10","10"],tempo:"3/0/1/1",cue:"Long head stretch. Add weight from Phase 2."},
          {id:"p3d5c2",name:"Farmer's Carry — Heavier",sets:4,repsScheme:["40m","40m","40m","40m"],tempo:"—",cue:"Increase load. Grip and gait conditioning."},
        ]},
      ],
    },
  ],

  // ── PHASE 4 ─────────────────────────────────────────────────────────────────
  4: [
    {
      id:"p4d1",day:"01",label:"PUSH A",sub:"Max Strength · Quad · Chest",color:"#58A45C",
      series:[
        {id:"p4d1a",name:"BARBELL WORK",type:"straight",exercises:[
          {id:"p4d1a1",name:"Barbell Back Squat — Heavy",sets:5,repsScheme:["5","3","3","3","3"],tempo:"3/1/X/0",cue:"Progressive overload. Add 5 lbs per session when possible. This is your long-term strength base."},
        ]},
        {id:"p4d1b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p4d1b1",name:"Hack Squat — Volume",sets:4,repsScheme:["10","10","10","10"],tempo:"2/0/X/0",cue:"After heavy squats. Quad pump and volume work."},
          {id:"p4d1b2",name:"Single Leg Curl — Heavy",sets:4,repsScheme:["8","8","8","8"],tempo:"4/1/X/1",cue:"Maximum hamstring development. Heaviest yet."},
        ]},
        {id:"p4d1c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p4d1c1",name:"Barbell Bench Press — Heavy",sets:4,repsScheme:["5","5","5","5"],tempo:"3/1/X/0",cue:"Controlled. 1-sec pause at chest. Progressive load."},
          {id:"p4d1c2",name:"Weighted Dips",sets:3,repsScheme:["10","10","10"],tempo:"3/0/X/0",cue:"If cleared. Upright torso for chest emphasis."},
        ]},
      ],
    },
    {
      id:"p4d2",day:"02",label:"PULL A",sub:"Conventional Deadlift · Back · Bicep",color:"#58A45C",
      series:[
        {id:"p4d2a",name:"BARBELL WORK",type:"straight",exercises:[
          {id:"p4d2a1",name:"Conventional Deadlift",sets:4,repsScheme:["4","4","4","4"],tempo:"3/0/X/0",cue:"The lift is back. Full hip extension. Lock out completely. Progressive overload every 1–2 weeks."},
        ]},
        {id:"p4d2b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p4d2b1",name:"Weighted Pull-Up",sets:4,repsScheme:["6","6","6","6"],tempo:"2/0/X/1",cue:"Full ROM. 1-sec squeeze. Add weight progressively."},
          {id:"p4d2b2",name:"Barbell Row — Pendlay Style",sets:4,repsScheme:["6","6","6","6"],tempo:"3/1/X/0",cue:"Bar to floor each rep. Explosive pull. Full back development."},
        ]},
        {id:"p4d2c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p4d2c1",name:"Barbell Curl",sets:4,repsScheme:["8","8","8","8"],tempo:"2/0/1/1",cue:"Heavy bicep work. Supinate. 1-sec squeeze at top."},
          {id:"p4d2c2",name:"Face Pull — Heavy",sets:3,repsScheme:["15","15","15"],tempo:"2/0/1/1",cue:"Shoulder health maintained as loads increase."},
        ]},
      ],
    },
    {
      id:"p4d3",day:"03",label:"ATHLETIC",sub:"Run Protocol · Performance",color:"#58A45C",
      series:[
        {id:"p4d3a",name:"MOVEMENT PREP",type:"straight",exercises:[
          {id:"p4d3a1",name:"Dynamic Warm-Up Circuit",sets:1,repsScheme:["10 min"],tempo:"—",cue:"Leg swings, hip circles, A-skips, high knees. Running prep."},
        ]},
        {id:"p4d3b",name:"RUN INTERVALS",type:"straight",exercises:[
          {id:"p4d3b1",name:"Structured Run — Zone 3/4 Intervals",sets:5,repsScheme:["4 min run","4 min run","4 min run","4 min run","4 min run"],tempo:"—",cue:"4 min at moderate effort / 2 min walk. HR up to 155. This is ultra runner territory returning."},
        ]},
        {id:"p4d3c",name:"ZONE 2 CARDIO",type:"straight",exercises:[
          {id:"p4d3c1",name:"Easy Run or Bike Cooldown",sets:1,repsScheme:["20 min"],tempo:"—",cue:"Bring HR back down. Conversational pace. Enjoy it."},
        ]},
      ],
    },
    {
      id:"p4d4",day:"04",label:"PUSH B",sub:"Overhead Strength · Athletic",color:"#58A45C",
      series:[
        {id:"p4d4a",name:"BARBELL WORK",type:"straight",exercises:[
          {id:"p4d4a1",name:"Barbell Overhead Press — Heavy",sets:5,repsScheme:["5","3","3","3","3"],tempo:"2/1/X/0",cue:"Standing. Full body tension. Progressive overload. The athletic press."},
        ]},
        {id:"p4d4b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p4d4b1",name:"Bulgarian Split Squat — Weighted",sets:4,repsScheme:["8","8","8","8"],tempo:"3/1/X/0",cue:"DB or barbell. Maximum unilateral strength. Athletic carry-over."},
          {id:"p4d4b2",name:"Cable Lateral Raise — Heavy",sets:4,repsScheme:["12","12","12","12"],tempo:"2/0/1/0",cue:"Capped delt development. CBum aesthetic maintained."},
        ]},
        {id:"p4d4c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p4d4c1",name:"Dumbbell Incline Press",sets:3,repsScheme:["10","10","10"],tempo:"3/0/X/0",cue:"Upper chest. Heavier than Phase 2. Same execution."},
          {id:"p4d4c2",name:"Overhead Tricep Extension — Cable",sets:3,repsScheme:["12","12","12"],tempo:"3/0/X/0",cue:"Long head. Heavy but controlled."},
        ]},
      ],
    },
    {
      id:"p4d5",day:"05",label:"PULL B",sub:"Back Width · Hinge · Full Athletic",color:"#58A45C",
      series:[
        {id:"p4d5a",name:"BARBELL WORK",type:"straight",exercises:[
          {id:"p4d5a1",name:"Trap Bar Deadlift or Sumo Deadlift",sets:4,repsScheme:["5","5","5","5"],tempo:"3/0/X/0",cue:"Variation for longevity. Trap bar reduces spinal shear. This is the forever lift."},
        ]},
        {id:"p4d5b",name:"B1/B2 SERIES",type:"superset",exercises:[
          {id:"p4d5b1",name:"Weighted Pull-Up — Max Effort",sets:4,repsScheme:["5","5","5","5"],tempo:"2/0/X/1",cue:"Heaviest weighted pull-up work. Peak back width."},
          {id:"p4d5b2",name:"Standing Calf Raise — Heavy",sets:4,repsScheme:["12","12","12","12"],tempo:"2/2/X/1",cue:"Gastroc focus. Running performance."},
        ]},
        {id:"p4d5c",name:"C1/C2 SERIES",type:"superset",exercises:[
          {id:"p4d5c1",name:"Hammer Curl — Heavy",sets:3,repsScheme:["10","10","10"],tempo:"2/0/1/1",cue:"Brachialis. Arm thickness. Progressive."},
          {id:"p4d5c2",name:"Farmer's Carry — Max Load",sets:4,repsScheme:["40m","40m","40m","40m"],tempo:"—",cue:"Heaviest carry yet. The ultra runner's finisher."},
        ]},
      ],
    },
  ],
};

// ─── AUDIO ────────────────────────────────────────────────────────────────────
function useBeep() {
  const ctx=useRef(null);
  const gc=()=>{if(!ctx.current)try{ctx.current=new(window.AudioContext||window.webkitAudioContext)();}catch{}return ctx.current;};
  const beep=useCallback((f=880,d=0.12,v=0.4)=>{try{const c=gc();if(!c)return;const o=c.createOscillator(),g=c.createGain();o.connect(g);g.connect(c.destination);o.frequency.value=f;o.type="sine";g.gain.setValueAtTime(v,c.currentTime);g.gain.exponentialRampToValueAtTime(0.001,c.currentTime+d);o.start(c.currentTime);o.stop(c.currentTime+d);}catch{}},[]);
  const chime=useCallback(()=>{beep(660,0.1,0.3);setTimeout(()=>beep(880,0.1,0.35),140);setTimeout(()=>beep(1100,0.2,0.5),280);},[beep]);
  return{beep,chime};
}

// ─── STORAGE ──────────────────────────────────────────────────────────────────
const LS="jackedlete_v2";
function load(){try{const r=localStorage.getItem(LS);return r?JSON.parse(r):{phase:2,logs:{},done:{}};}catch{return{phase:2,logs:{},done:{}};}}
function save(s){try{localStorage.setItem(LS,JSON.stringify(s));}catch{}}
function wk(){const d=new Date(),j=new Date(d.getFullYear(),0,1);return`${d.getFullYear()}-W${Math.ceil(((d-j)/86400000+j.getDay()+1)/7)}`;}
function fd(){return new Date().toLocaleDateString("en-US",{month:"short",day:"numeric",year:"numeric"});}
function ft(s){return`${Math.floor(s/60)}:${(s%60).toString().padStart(2,"0")}`;}

// ─── APP ──────────────────────────────────────────────────────────────────────
function App() {
  const [store,setStore]=useState(load);
  const [activeDay,setActiveDay]=useState(0);
  const [view,setView]=useState("workout"); // workout | phases | history
  const [timer,setTimer]=useState(null);
  const [toast,setToast]=useState(null);
  const [showAdvance,setShowAdvance]=useState(false);
  const tickRef=useRef(null);
  const weekKey=wk();
  const {beep,chime}=useBeep();

  useEffect(()=>{save(store);},[store]);

  useEffect(()=>{
    if(!timer?.active||timer.remaining<=0)return;
    tickRef.current=setTimeout(()=>{
      const n=timer.remaining-1;
      if([10,5,3,2,1].includes(n))beep(n<=3?880:660,0.08,0.25);
      if(n===0)chime();
      setTimer(t=>t?{...t,remaining:n,active:n>0}:t);
    },1000);
    return()=>clearTimeout(tickRef.current);
  },[timer,beep,chime]);

  const startTimer=useCallback((secs,label,cardiac,color)=>{
    if(!secs)return;
    clearTimeout(tickRef.current);
    beep(440,0.08,0.25);
    setTimer({total:secs,remaining:secs,label,cardiac,color,active:true});
  },[beep]);

  const dismissTimer=()=>{clearTimeout(tickRef.current);setTimer(null);};
  const adjTimer=d=>setTimer(t=>t?{...t,remaining:Math.max(0,t.remaining+d),total:Math.max(0,t.total+d)}:t);
  const pauseTimer=()=>setTimer(t=>t?{...t,active:!t.active}:t);
  const addTimer=s=>setTimer(t=>t?{...t,remaining:t.remaining+s,total:t.total+s,active:true}:t);

  const showToast=(msg,type="ok")=>{setToast({msg,type});setTimeout(()=>setToast(null),2400);};

  const phase=store.phase;
  const phaseData=PHASES[phase-1];
  const program=PROGRAMS[phase]||PROGRAMS[2];
  const currentDay=program[activeDay];

  const logSet=(exId,si,w,r)=>{
    const k=`${weekKey}_${phase}_${activeDay}_${exId}_${si}`;
    setStore(p=>({...p,logs:{...p.logs,[k]:{weight:w,reps:r,date:fd()}}}));
  };
  const getLog=(exId,si)=>store.logs[`${weekKey}_${phase}_${activeDay}_${exId}_${si}`]||null;
  const isDone=(exId,si)=>!!store.done[`${phase}_${activeDay}_${exId}_${si}`];
  const toggleDone=(exId,si)=>setStore(p=>({...p,done:{...p.done,[`${phase}_${activeDay}_${exId}_${si}`]:!p.done[`${phase}_${activeDay}_${exId}_${si}`]}}));

  const progress=(()=>{
    let t=0,d=0;
    program[activeDay].series.forEach(s=>s.exercises.forEach(ex=>{
      for(let i=0;i<ex.sets;i++){t++;if(isDone(ex.id,i))d++;}
    }));
    return t?Math.round((d/t)*100):0;
  })();

  const advancePhase=()=>{
    if(phase<4){setStore(p=>({...p,phase:p.phase+1}));setShowAdvance(false);setActiveDay(0);showToast(`Advanced to Phase ${phase+1}!`);}
  };

  return(
    <div style={{minHeight:"100vh",background:"#0A0A0A",fontFamily:"'Barlow Condensed','Arial Narrow',sans-serif",color:"#E8E8E8",userSelect:"none"}}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@300;400;500;600;700;800;900&family=Barlow:wght@300;400;500;600&display=swap');
        *{box-sizing:border-box;margin:0;padding:0;}
        ::-webkit-scrollbar{width:3px}::-webkit-scrollbar-track{background:#111}::-webkit-scrollbar-thumb{background:#2A2A2A;border-radius:2px}
        input[type=number]{-moz-appearance:textfield;background:#181818;border:1px solid #2C2C2C;color:#DDD;border-radius:6px;padding:5px 6px;font-family:'Barlow',sans-serif;font-size:13px;width:100%;outline:none;transition:border-color .15s;text-align:center;}
        input[type=number]::-webkit-outer-spin-button,input[type=number]::-webkit-inner-spin-button{-webkit-appearance:none}
        input[type=number]:focus{border-color:#C9A84C}
        .hov{transition:all .12s;cursor:pointer}.hov:hover{filter:brightness(1.2);transform:scale(1.03)}
        .rh:hover{background:rgba(255,255,255,0.015)}
        @keyframes fu{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
        @keyframes ts{from{opacity:0;transform:translateY(16px) scale(.95)}to{opacity:1;transform:translateY(0) scale(1)}}
        @keyframes tw{from{opacity:0;transform:translateY(60px)}to{opacity:1;transform:translateY(0)}}
        @keyframes cp{0%,100%{opacity:1}50%{opacity:.4}}
        .fb{animation:fu .28s ease forwards}
        .twrap{animation:tw .22s cubic-bezier(.34,1.4,.64,1) forwards}
      `}</style>

      {toast&&<div style={{position:"fixed",bottom:96,left:"50%",transform:"translateX(-50%)",background:toast.type==="ok"?"#182818":"#281818",border:`1px solid ${toast.type==="ok"?"#4A8A4A":"#8A3A3A"}`,color:toast.type==="ok"?"#7ED881":"#E87B6E",padding:"9px 18px",borderRadius:8,fontSize:12,fontFamily:"Barlow,sans-serif",fontWeight:600,zIndex:9999,animation:"ts .18s ease",boxShadow:"0 4px 20px rgba(0,0,0,.7)",whiteSpace:"nowrap"}}>{toast.msg}</div>}

      {timer&&<RestTimer timer={timer} onDismiss={dismissTimer} onAdjust={adjTimer} onPause={pauseTimer} onAdd={addTimer}/>}

      {showAdvance&&<AdvanceModal phase={phase} phases={PHASES} onConfirm={advancePhase} onCancel={()=>setShowAdvance(false)}/>}

      {/* HEADER */}
      <div style={{background:"#0D0D0D",borderBottom:`2px solid ${phaseData.color}`,padding:"0 14px",position:"sticky",top:0,zIndex:200}}>
        <div style={{maxWidth:680,margin:"0 auto",display:"flex",alignItems:"center",justifyContent:"space-between",height:52}}>
          <div style={{display:"flex",alignItems:"baseline",gap:8}}>
            <span style={{fontSize:22,fontWeight:900,color:phaseData.color,letterSpacing:".12em"}}>JACKEDLETE</span>
            <div style={{background:phaseData.color,color:"#000",fontSize:8,fontWeight:800,borderRadius:4,padding:"2px 6px",letterSpacing:".1em"}}>PHASE {phase}</div>
          </div>
          <div style={{display:"flex",gap:5}}>
            {["workout","phases","history"].map(v=>(
              <button key={v} onClick={()=>setView(v)} style={{background:view===v?phaseData.color:"transparent",color:view===v?"#000":"#666",border:`1px solid ${view===v?phaseData.color:"#2A2A2A"}`,borderRadius:6,padding:"4px 9px",fontSize:9,fontWeight:700,letterSpacing:".1em",cursor:"pointer",textTransform:"uppercase",transition:"all .12s"}}>{v}</button>
            ))}
          </div>
        </div>
      </div>

      {view==="workout"&&<WorkoutView program={program} activeDay={activeDay} setActiveDay={setActiveDay} currentDay={currentDay} progress={progress} phaseData={phaseData} logSet={logSet} getLog={getLog} isDone={isDone} toggleDone={toggleDone} showToast={showToast} startTimer={startTimer} phase={phase} onSuggestAdvance={()=>setShowAdvance(true)}/>}
      {view==="phases"&&<PhasesView phases={PHASES} currentPhase={phase} onAdvance={()=>setShowAdvance(true)}/>}
      {view==="history"&&<HistoryView store={store} weekKey={weekKey} program={program} phase={phase}/>}
    </div>
  );
}

// ─── ADVANCE MODAL ────────────────────────────────────────────────────────────
function AdvanceModal({phase,phases,onConfirm,onCancel}) {
  const next=phases[phase]; // phase is 1-indexed, array is 0-indexed
  if(!next)return null;
  return(
    <div style={{position:"fixed",inset:0,background:"rgba(0,0,0,.85)",zIndex:400,display:"flex",alignItems:"center",justifyContent:"center",padding:20}}>
      <div style={{background:"#131313",border:`2px solid ${next.color}`,borderRadius:16,padding:24,maxWidth:380,width:"100%"}}>
        <div style={{fontSize:11,color:"#666",fontWeight:700,letterSpacing:".15em",marginBottom:4}}>PHASE ADVANCE</div>
        <div style={{fontSize:22,fontWeight:900,color:next.color,letterSpacing:".1em",marginBottom:4}}>PHASE {phase+1} — {next.name}</div>
        <div style={{fontSize:12,color:"#888",fontFamily:"Barlow,sans-serif",marginBottom:16,lineHeight:1.5}}>{next.description}</div>

        <div style={{marginBottom:16}}>
          <div style={{fontSize:10,color:"#555",fontWeight:700,letterSpacing:".12em",marginBottom:8}}>WHAT UNLOCKS</div>
          {next.unlocks.map((u,i)=>(
            <div key={i} style={{display:"flex",alignItems:"center",gap:8,marginBottom:6}}>
              <div style={{width:6,height:6,borderRadius:"50%",background:next.color,flexShrink:0}}/>
              <span style={{fontSize:11,color:"#CCC",fontFamily:"Barlow,sans-serif"}}>{u}</span>
            </div>
          ))}
        </div>

        <div style={{background:"rgba(192,57,43,.08)",border:"1px solid rgba(192,57,43,.2)",borderRadius:8,padding:"10px 12px",marginBottom:16}}>
          <div style={{fontSize:9,color:"#E87B6E",fontWeight:700,letterSpacing:".12em",marginBottom:4}}>⚠️  CONFIRM BEFORE ADVANCING</div>
          <div style={{fontSize:10,color:"#C07060",fontFamily:"Barlow,sans-serif",lineHeight:1.5}}>Only advance when your cardiologist has cleared you for increased intensity. Do not self-advance based on how you feel alone.</div>
        </div>

        <div style={{display:"flex",gap:10}}>
          <button className="hov" onClick={onCancel} style={{flex:1,height:42,borderRadius:10,background:"#1A1A1A",border:"1px solid #2A2A2A",color:"#666",fontSize:12,fontWeight:700,cursor:"pointer"}}>NOT YET</button>
          <button className="hov" onClick={onConfirm} style={{flex:1,height:42,borderRadius:10,background:next.color,border:"none",color:"#000",fontSize:12,fontWeight:800,letterSpacing:".08em",cursor:"pointer"}}>ADVANCE →</button>
        </div>
      </div>
    </div>
  );
}

// ─── PHASES VIEW ──────────────────────────────────────────────────────────────
function PhasesView({phases,currentPhase,onAdvance}) {
  return(
    <div style={{maxWidth:680,margin:"0 auto",padding:"14px 14px 80px"}}>
      <div style={{marginBottom:18}}>
        <div style={{fontSize:21,fontWeight:900,color:"#EEE",letterSpacing:".1em"}}>PROGRESSION PHASES</div>
        <div style={{fontSize:11,color:"#444",fontFamily:"Barlow,sans-serif",marginTop:2}}>Your roadmap back to full athletic function</div>
      </div>

      {phases.map((p,i)=>{
        const isCurrent=p.id===currentPhase;
        const isPast=p.id<currentPhase;
        const isNext=p.id===currentPhase+1;
        return(
          <div key={p.id} style={{background:"#0F0F0F",border:`1px solid ${isCurrent?p.color:"#1E1E1E"}`,borderLeft:`4px solid ${isPast?"#333":p.color}`,borderRadius:12,marginBottom:12,overflow:"hidden",opacity:p.id>currentPhase+1?.5:1}}>
            {/* Phase header */}
            <div style={{padding:"12px 14px",background:isCurrent?`${p.color}11`:"#141414",display:"flex",alignItems:"center",justifyContent:"space-between"}}>
              <div>
                <div style={{display:"flex",alignItems:"center",gap:8,marginBottom:2}}>
                  <span style={{fontSize:18,fontWeight:900,color:isPast?"#444":p.color,letterSpacing:".1em"}}>PHASE {p.id} — {p.name}</span>
                  {isCurrent&&<span style={{background:p.color,color:"#000",fontSize:8,fontWeight:800,borderRadius:4,padding:"2px 6px",letterSpacing:".08em"}}>CURRENT</span>}
                  {isPast&&<span style={{background:"#222",color:"#555",fontSize:8,fontWeight:800,borderRadius:4,padding:"2px 6px",letterSpacing:".08em"}}>COMPLETED</span>}
                </div>
                <div style={{fontSize:11,color:"#666",fontFamily:"Barlow,sans-serif"}}>{p.weeks} · HR Ceiling {p.hrCeiling} BPM · RPE ≤ {p.rpe}</div>
              </div>
              {isPast&&<span style={{fontSize:24,color:"#3A3A3A"}}>✓</span>}
            </div>

            <div style={{padding:"12px 14px"}}>
              <div style={{fontSize:11,color:"#888",fontFamily:"Barlow,sans-serif",lineHeight:1.6,marginBottom:12}}>{p.description}</div>

              <div style={{display:"flex",gap:8,marginBottom:12,flexWrap:"wrap"}}>
                <div style={{background:"#181818",border:"1px solid #222",borderRadius:7,padding:"5px 10px"}}>
                  <div style={{fontSize:8,color:"#444",fontWeight:700,letterSpacing:".1em",marginBottom:2}}>CARDIO TARGET</div>
                  <div style={{fontSize:10,color:p.color,fontWeight:700}}>{p.cardioTarget}</div>
                </div>
              </div>

              {/* Unlocks */}
              <div style={{marginBottom:isCurrent&&p.criteria.length>0?12:0}}>
                <div style={{fontSize:9,color:"#444",fontWeight:700,letterSpacing:".12em",marginBottom:6}}>PHASE UNLOCKS</div>
                <div style={{display:"flex",gap:5,flexWrap:"wrap"}}>
                  {p.unlocks.map((u,j)=>(
                    <div key={j} style={{background:"#181818",border:`1px solid ${isPast?"#2A2A2A":p.color+"33"}`,borderRadius:6,padding:"3px 8px",fontSize:9,color:isPast?"#555":p.color,fontWeight:700}}>{u}</div>
                  ))}
                </div>
              </div>

              {/* Advance criteria */}
              {isCurrent&&p.criteria.length>0&&(
                <div>
                  <div style={{fontSize:9,color:"#444",fontWeight:700,letterSpacing:".12em",marginBottom:6,marginTop:12}}>CRITERIA TO ADVANCE</div>
                  {p.criteria.map((c,j)=>(
                    <div key={j} style={{display:"flex",alignItems:"flex-start",gap:8,marginBottom:6}}>
                      <div style={{width:5,height:5,borderRadius:"50%",background:"#333",flexShrink:0,marginTop:4}}/>
                      <span style={{fontSize:10,color:"#888",fontFamily:"Barlow,sans-serif",lineHeight:1.5}}>{c}</span>
                    </div>
                  ))}
                  <button className="hov" onClick={onAdvance} style={{marginTop:12,width:"100%",height:40,borderRadius:9,background:"#181818",border:`1px solid ${phases[currentPhase]?.color||"#333"}`,color:phases[currentPhase]?.color||"#666",fontSize:11,fontWeight:800,letterSpacing:".1em",cursor:"pointer",display:"flex",alignItems:"center",justifyContent:"center",gap:6}}>
                    I'M READY — ADVANCE TO PHASE {p.id+1} →
                  </button>
                </div>
              )}
            </div>
          </div>
        );
      })}
    </div>
  );
}

// ─── WORKOUT VIEW ─────────────────────────────────────────────────────────────
function WorkoutView({program,activeDay,setActiveDay,currentDay,progress,phaseData,logSet,getLog,isDone,toggleDone,showToast,startTimer,phase,onSuggestAdvance}) {
  return(
    <div style={{maxWidth:680,margin:"0 auto",padding:"12px 12px 320px"}}>
      {/* Phase banner */}
      <div style={{background:`${phaseData.color}11`,border:`1px solid ${phaseData.color}33`,borderRadius:10,padding:"8px 12px",marginBottom:12,display:"flex",alignItems:"center",justifyContent:"space-between"}}>
        <div>
          <div style={{fontSize:10,color:phaseData.color,fontWeight:800,letterSpacing:".12em"}}>PHASE {phase} — {phaseData.name}</div>
          <div style={{fontSize:10,color:"#666",fontFamily:"Barlow,sans-serif"}}>{phaseData.sub} · HR ≤ {phaseData.hrCeiling} · RPE ≤ {phaseData.rpe}</div>
        </div>
        <button className="hov" onClick={()=>{}} style={{background:"transparent",border:`1px solid ${phaseData.color}44`,borderRadius:6,padding:"3px 8px",color:phaseData.color,fontSize:9,fontWeight:700,cursor:"pointer"}} onClick={onSuggestAdvance}>ADVANCE?</button>
      </div>

      {/* Day selector */}
      <div style={{display:"flex",gap:6,marginBottom:14,overflowX:"auto",paddingBottom:3}}>
        {program.map((d,i)=>(
          <button key={d.id} className="hov" onClick={()=>setActiveDay(i)} style={{flex:"0 0 auto",background:activeDay===i?phaseData.color:"#131313",border:`1px solid ${activeDay===i?phaseData.color:"#222"}`,borderRadius:10,padding:"8px 12px",cursor:"pointer",display:"flex",flexDirection:"column",alignItems:"center",gap:1,minWidth:64}}>
            <span style={{fontSize:16,fontWeight:900,color:activeDay===i?"#000":"#555",lineHeight:1}}>{d.day}</span>
            <span style={{fontSize:8,fontWeight:800,color:activeDay===i?"#000":phaseData.color,letterSpacing:".08em"}}>{d.label}</span>
          </button>
        ))}
      </div>

      {/* Day header */}
      <div style={{background:"#131313",border:"1px solid #222",borderLeft:`4px solid ${phaseData.color}`,borderRadius:12,padding:"12px 14px",marginBottom:12,display:"flex",alignItems:"center",justifyContent:"space-between"}}>
        <div>
          <div style={{fontSize:19,fontWeight:900,color:phaseData.color,letterSpacing:".1em"}}>DAY {currentDay.day} — {currentDay.label}</div>
          <div style={{fontSize:11,color:"#666",fontWeight:500,marginTop:1}}>{currentDay.sub}</div>
        </div>
        <Ring progress={progress} color={phaseData.color}/>
      </div>

      {/* Cardiac banner */}
      <div style={{background:"rgba(192,57,43,.07)",border:"1px solid rgba(192,57,43,.22)",borderRadius:8,padding:"6px 10px",marginBottom:12,display:"flex",alignItems:"center",gap:6}}>
        <span style={{fontSize:13}}>❤️</span>
        <span style={{fontSize:9,color:"#E87B6E",fontWeight:600,letterSpacing:".04em"}}>HR MAX {phaseData.hrCeiling} BPM · NO VALSALVA · RPE ≤ {phaseData.rpe} · STOP: chest pressure / dizziness / jaw pain</span>
      </div>

      {/* Rest legend */}
      <div style={{display:"flex",gap:5,marginBottom:12,flexWrap:"wrap"}}>
        {[{l:"A SERIES",t:phase>=3?"3:00/2:30":"2:00/2:30",c:"#C9A84C"},{l:"B SERIES",t:"1:30",c:"#7EB8D4"},{l:"C SERIES",t:"1:00",c:"#A8D4A0"}].map(r=>(
          <div key={r.l} style={{display:"flex",alignItems:"center",gap:4,background:"#131313",border:"1px solid #1E1E1E",borderRadius:6,padding:"3px 7px"}}>
            <div style={{width:4,height:4,borderRadius:"50%",background:r.c}}/>
            <span style={{fontSize:8,color:"#444",fontWeight:700}}>{r.l}</span>
            <span style={{fontSize:8,color:r.c,fontWeight:800}}>{r.t}</span>
          </div>
        ))}
      </div>

      {currentDay.series.map((s,si)=>(
        <SeriesBlock key={s.id} series={s} dayLabel={currentDay.label} phaseColor={phaseData.color} logSet={logSet} getLog={getLog} isDone={isDone} toggleDone={toggleDone} showToast={showToast} startTimer={startTimer} delay={si*70}/>
      ))}
    </div>
  );
}

function Ring({progress,color}){
  const r=20,C=2*Math.PI*r;
  return(
    <div style={{position:"relative",width:50,height:50,display:"flex",alignItems:"center",justifyContent:"center"}}>
      <svg width={50} height={50} style={{position:"absolute",transform:"rotate(-90deg)"}}>
        <circle cx={25} cy={25} r={r} fill="none" stroke="#1E1E1E" strokeWidth={3}/>
        <circle cx={25} cy={25} r={r} fill="none" stroke={color} strokeWidth={3} strokeDasharray={C} strokeDashoffset={C-(C*progress/100)} strokeLinecap="round" style={{transition:"stroke-dashoffset .4s ease"}}/>
      </svg>
      <span style={{fontSize:11,fontWeight:800,color,zIndex:1}}>{progress}%</span>
    </div>
  );
}

// ─── SERIES BLOCK ─────────────────────────────────────────────────────────────
function SeriesBlock({series,dayLabel,phaseColor,logSet,getLog,isDone,toggleDone,showToast,startTimer,delay}){
  const [open,setOpen]=useState(true);
  const sc=series.name.startsWith("A")||series.name.startsWith("BAR")||series.name.startsWith("RUN")?"#C9A84C":series.name.startsWith("B")?"#7EB8D4":series.name.startsWith("C")?"#A8D4A0":"#888";
  const rest=getRestInfo(series.name,dayLabel);
  return(
    <div className="fb" style={{background:"#0F0F0F",border:"1px solid #1E1E1E",borderRadius:12,marginBottom:10,overflow:"hidden",animationDelay:`${delay}ms`,opacity:0,animationFillMode:"forwards"}}>
      <div style={{display:"flex",alignItems:"center",justifyContent:"space-between",padding:"8px 12px",background:"#151515",borderBottom:open?"1px solid #1E1E1E":"none"}}>
        <div onClick={()=>setOpen(o=>!o)} style={{display:"flex",alignItems:"center",gap:8,flex:1,cursor:"pointer"}}>
          <div style={{width:3,height:14,background:sc,borderRadius:2}}/>
          <span style={{fontSize:10,fontWeight:800,color:sc,letterSpacing:".15em"}}>{series.name}</span>
          {series.type==="superset"&&<span style={{fontSize:7,fontWeight:700,color:"#000",background:sc,borderRadius:3,padding:"1px 4px",letterSpacing:".08em"}}>SUPERSET</span>}
        </div>
        <div style={{display:"flex",alignItems:"center",gap:6}}>
          {rest.secs>0&&<button className="hov" onClick={()=>startTimer(rest.secs,rest.label,rest.cardiac,sc)} style={{display:"flex",alignItems:"center",gap:4,background:"#1A1A1A",border:`1px solid ${sc}33`,borderRadius:6,padding:"3px 8px",color:sc,fontSize:9,fontWeight:800,cursor:"pointer"}}><span>⏱</span>{rest.label}</button>}
          <span onClick={()=>setOpen(o=>!o)} style={{color:"#333",fontSize:12,cursor:"pointer"}}>{open?"▲":"▼"}</span>
        </div>
      </div>
      {open&&series.exercises.map((ex,ei)=>(
        <ExBlock key={ex.id} ex={ex} isLast={ei===series.exercises.length-1} sc={sc} rest={rest} logSet={logSet} getLog={getLog} isDone={isDone} toggleDone={toggleDone} showToast={showToast} startTimer={startTimer}/>
      ))}
    </div>
  );
}

// ─── EXERCISE BLOCK ───────────────────────────────────────────────────────────
function ExBlock({ex,isLast,sc,rest,logSet,getLog,isDone,toggleDone,showToast,startTimer}){
  return(
    <div style={{borderBottom:isLast?"none":"1px solid #181818"}}>
      <div style={{padding:"8px 12px 4px"}}>
        <div style={{fontSize:13,fontWeight:700,color:"#E8E8E8",letterSpacing:".04em",marginBottom:3}}>{ex.name}</div>
        <div style={{display:"flex",gap:6,flexWrap:"wrap",alignItems:"center"}}>
          <Pill label="TEMPO" val={ex.tempo} color="#C9A84C"/>
          <Pill label="SETS" val={ex.sets} color={sc}/>
          <Pill label="REST" val={rest.secs>0?rest.label:"—"} color="#555"/>
        </div>
        <div style={{marginTop:3,fontSize:10,color:"#555",fontFamily:"Barlow,sans-serif",fontStyle:"italic",lineHeight:1.4}}>★ {ex.cue}</div>
      </div>
      <div style={{padding:"0 12px 8px"}}>
        <div style={{display:"grid",gridTemplateColumns:"22px 48px 1fr 1fr 30px 30px",gap:4,alignItems:"center",padding:"2px 0",borderBottom:"1px solid #1A1A1A",marginBottom:2}}>
          {["#","TARGET","WEIGHT","REPS","⏱","✓"].map(h=>(
            <span key={h} style={{fontSize:7.5,color:"#333",fontWeight:700,letterSpacing:".08em",textAlign:["WEIGHT","REPS"].includes(h)?"center":"left"}}>{h}</span>
          ))}
        </div>
        {Array.from({length:ex.sets}).map((_,si)=>(
          <SetRow key={si} setNum={si+1} target={ex.repsScheme[si]||ex.repsScheme[ex.repsScheme.length-1]} exId={ex.id} setIdx={si} sc={sc} rest={rest} logSet={logSet} getLog={getLog} isDone={isDone} toggleDone={toggleDone} showToast={showToast} startTimer={startTimer}/>
        ))}
      </div>
    </div>
  );
}

// ─── SET ROW ──────────────────────────────────────────────────────────────────
function SetRow({setNum,target,exId,setIdx,sc,rest,logSet,getLog,isDone,toggleDone,showToast,startTimer}){
  const ex=getLog(exId,setIdx);
  const [w,setW]=useState(ex?.weight||"");
  const [r,setR]=useState(ex?.reps||"");
  const done=isDone(exId,setIdx);
  const complete=()=>{
    if(!w&&!r&&!["—","35–40 min","35–45 min","30–35 min","40m","10 min","20 min","15–20 min"].includes(target)){showToast("Enter weight or reps first","err");return;}
    logSet(exId,setIdx,w,r);
    toggleDone(exId,setIdx);
    if(!done){showToast(`Set ${setNum} logged ✓`);if(rest.secs>0)startTimer(rest.secs,rest.label,rest.cardiac,sc);}
  };
  return(
    <div className="rh" style={{display:"grid",gridTemplateColumns:"22px 48px 1fr 1fr 30px 30px",gap:4,alignItems:"center",padding:"3px 0",opacity:done?.4:1,transition:"opacity .2s"}}>
      <div style={{width:18,height:18,borderRadius:4,background:done?sc:"#1A1A1A",border:`1px solid ${done?sc:"#252525"}`,display:"flex",alignItems:"center",justifyContent:"center",fontSize:8,fontWeight:800,color:done?"#000":"#3A3A3A",transition:"all .2s"}}>{setNum}</div>
      <div style={{fontSize:11,fontWeight:800,color:"#C9A84C",letterSpacing:".03em"}}>{target}</div>
      <input type="number" placeholder="lbs" value={w} onChange={e=>setW(e.target.value)} min={0} step={2.5} disabled={done} style={{opacity:done?.2:1,fontSize:12,padding:"4px 5px"}}/>
      <input type="number" placeholder="reps" value={r} onChange={e=>setR(e.target.value)} min={0} disabled={done} style={{opacity:done?.2:1,fontSize:12,padding:"4px 5px"}}/>
      <button className="hov" onClick={()=>rest.secs>0&&startTimer(rest.secs,rest.label,rest.cardiac,sc)} style={{width:26,height:26,borderRadius:5,background:"#141414",border:"1px solid #1E1E1E",color:rest.secs>0?sc:"#2A2A2A",fontSize:11,display:"flex",alignItems:"center",justifyContent:"center",cursor:"pointer",opacity:rest.secs>0?1:.3}}>⏱</button>
      <button className="hov" onClick={complete} style={{width:26,height:26,borderRadius:5,background:done?sc:"#141414",border:`1px solid ${done?sc:"#1E1E1E"}`,color:done?"#000":"#3A3A3A",fontSize:done?10:13,display:"flex",alignItems:"center",justifyContent:"center",cursor:"pointer",transition:"all .2s"}}>{done?"✓":"○"}</button>
    </div>
  );
}

function Pill({label,val,color}){
  return(
    <div style={{display:"flex",alignItems:"center",gap:3,background:"#181818",border:"1px solid #222",borderRadius:4,padding:"1px 5px"}}>
      <span style={{fontSize:7.5,color:"#3A3A3A",fontWeight:700,letterSpacing:".1em"}}>{label}</span>
      <span style={{fontSize:9.5,color,fontWeight:800}}>{val}</span>
    </div>
  );
}

// ─── REST TIMER ───────────────────────────────────────────────────────────────
function RestTimer({timer,onDismiss,onAdjust,onPause,onAdd}){
  const pct=timer.total>0?timer.remaining/timer.total:0;
  const done=timer.remaining===0;
  const low=!done&&timer.remaining<=10;
  const arc=done?"#58A45C":low?"#E87B6E":(timer.color||"#C9A84C");
  const R=52,C=2*Math.PI*R;
  return(
    <div className="twrap" style={{position:"fixed",bottom:0,left:0,right:0,zIndex:300,background:done?"#0C1A0C":"#0D0D0D",borderTop:`2px solid ${arc}`,boxShadow:"0 -6px 32px rgba(0,0,0,.85)",padding:"14px 14px 28px",transition:"background .5s"}}>
      <div style={{maxWidth:540,margin:"0 auto"}}>
        <div style={{display:"flex",alignItems:"flex-start",justifyContent:"space-between",marginBottom:10}}>
          <div>
            <div style={{fontSize:8,color:"#555",fontWeight:700,letterSpacing:".18em",marginBottom:1}}>REST TIMER</div>
            <div style={{fontSize:13,fontWeight:800,color:arc,letterSpacing:".08em"}}>{timer.label}</div>
          </div>
          <button className="hov" onClick={onDismiss} style={{background:"#181818",border:"1px solid #2A2A2A",color:"#555",borderRadius:7,width:28,height:28,fontSize:13,display:"flex",alignItems:"center",justifyContent:"center",cursor:"pointer"}}>✕</button>
        </div>
        <div style={{display:"flex",gap:14,alignItems:"center"}}>
          <div style={{position:"relative",width:120,height:120,flexShrink:0}}>
            <svg width={120} height={120} style={{transform:"rotate(-90deg)"}}>
              <circle cx={60} cy={60} r={R} fill="none" stroke="#1C1C1C" strokeWidth={8}/>
              <circle cx={60} cy={60} r={R} fill="none" stroke={arc} strokeWidth={8} strokeDasharray={`${C*pct} ${C}`} strokeLinecap="round" style={{transition:"stroke-dasharray 0.95s linear,stroke .3s"}}/>
            </svg>
            <div style={{position:"absolute",inset:0,display:"flex",flexDirection:"column",alignItems:"center",justifyContent:"center"}}>
              <div style={{fontSize:done?22:34,fontWeight:900,color:done?"#58A45C":low?"#E87B6E":"#EEE",lineHeight:1,animation:low&&!done?"cp .7s infinite":"none",transition:"color .25s"}}>{done?"GO!":ft(timer.remaining)}</div>
              {!done&&<div style={{fontSize:8,color:"#333",marginTop:1,fontWeight:700}}>/ {ft(timer.total)}</div>}
            </div>
          </div>
          <div style={{flex:1,display:"flex",flexDirection:"column",gap:7}}>
            {timer.cardiac&&<div style={{background:"rgba(192,57,43,.07)",border:"1px solid rgba(192,57,43,.2)",borderRadius:7,padding:"5px 8px"}}><div style={{fontSize:7.5,color:"#E87B6E",fontWeight:700,letterSpacing:".12em",marginBottom:1}}>❤️  CARDIAC</div><div style={{fontSize:9,color:"#C07060",fontFamily:"Barlow,sans-serif",lineHeight:1.4}}>{timer.cardiac}</div></div>}
            <div style={{display:"flex",gap:4}}>
              {[-30,-15,+15,+30].map(d=>(
                <button key={d} className="hov" onClick={()=>onAdjust(d)} style={{flex:1,height:30,borderRadius:6,cursor:"pointer",background:"#181818",border:"1px solid #252525",color:d<0?"#E87B6E":"#7EB8D4",fontSize:10,fontWeight:800,display:"flex",alignItems:"center",justifyContent:"center"}}>{d>0?"+":""}{d}s</button>
              ))}
            </div>
            <div style={{display:"flex",gap:5}}>
              <button className="hov" onClick={onPause} style={{flex:1,height:36,borderRadius:8,cursor:"pointer",background:timer.active?"#181818":"#182818",border:`1px solid ${timer.active?"#2A2A2A":"#3A5A3A"}`,color:timer.active?"#777":"#58A45C",fontSize:11,fontWeight:800,letterSpacing:".08em",display:"flex",alignItems:"center",justifyContent:"center",gap:4}}>{timer.active?"⏸ PAUSE":"▶ RESUME"}</button>
              <button className="hov" onClick={onDismiss} style={{flex:1,height:36,borderRadius:8,cursor:"pointer",background:done?"#182818":"#181818",border:`1px solid ${done?"#4A8A4A":"#2A2A2A"}`,color:done?"#58A45C":"#666",fontSize:11,fontWeight:800,letterSpacing:".08em",display:"flex",alignItems:"center",justifyContent:"center",gap:4}}>{done?"✓ NEXT SET":"⏭ SKIP"}</button>
            </div>
            {!done&&<div style={{display:"flex",gap:4,alignItems:"center"}}><span style={{fontSize:8,color:"#2A2A2A",fontWeight:700}}>ADD:</span>{[30,60].map(s=><button key={s} className="hov" onClick={()=>onAdd(s)} style={{height:24,padding:"0 8px",borderRadius:5,cursor:"pointer",background:"#141414",border:"1px solid #1E1E1E",color:"#777",fontSize:9,fontWeight:700,display:"flex",alignItems:"center"}}>+{s}s</button>)}<span style={{fontSize:8,color:"#222"}}>if HR high</span></div>}
          </div>
        </div>
      </div>
    </div>
  );
}

// ─── HISTORY VIEW ─────────────────────────────────────────────────────────────
function HistoryView({store,weekKey,program,phase}){
  const byDay={};
  const exMap={};
  Object.values(PROGRAMS).forEach(prog=>prog.forEach(d=>d.series.forEach(s=>s.exercises.forEach(ex=>{exMap[ex.id]=ex.name;}))));
  Object.entries(store.logs).filter(([k])=>k.startsWith(weekKey)).forEach(([k,v])=>{
    const p=k.split("_");if(p.length<6)return;
    const ph=parseInt(p[1]),di=parseInt(p[2]),ei=p[3],si=parseInt(p[4]);
    const key=`ph${ph}_d${di}`;
    if(!byDay[key])byDay[key]={phase:ph,day:di,exercises:{}};
    if(!byDay[key].exercises[ei])byDay[key].exercises[ei]=[];
    byDay[key].exercises[ei].push({si,...v});
  });
  return(
    <div style={{maxWidth:680,margin:"0 auto",padding:"14px 14px 80px"}}>
      <div style={{marginBottom:16}}>
        <div style={{fontSize:20,fontWeight:900,color:"#EEE",letterSpacing:".1em"}}>THIS WEEK'S LOG</div>
        <div style={{fontSize:10,color:"#444",fontFamily:"Barlow,sans-serif",marginTop:2}}>Week {weekKey} · Saved to device · Resets each new week</div>
      </div>
      {Object.keys(byDay).length===0&&<div style={{background:"#0F0F0F",border:"1px solid #1E1E1E",borderRadius:12,padding:36,textAlign:"center"}}><div style={{fontSize:32,marginBottom:10}}>📋</div><div style={{fontSize:13,color:"#444",fontFamily:"Barlow,sans-serif"}}>Nothing logged yet this week.</div></div>}
      {Object.entries(byDay).map(([key,{phase:ph,day:di,exercises}])=>{
        const phData=PHASES[ph-1];
        const prog=PROGRAMS[ph]||PROGRAMS[2];
        const dayData=prog[di];
        if(!dayData||!phData)return null;
        return(
          <div key={key} style={{background:"#0F0F0F",border:"1px solid #1E1E1E",borderLeft:`4px solid ${phData.color}`,borderRadius:12,marginBottom:10,overflow:"hidden"}}>
            <div style={{background:"#141414",padding:"8px 12px",borderBottom:"1px solid #1A1A1A",display:"flex",alignItems:"center",gap:8}}>
              <span style={{fontSize:9,background:phData.color,color:"#000",fontWeight:800,borderRadius:3,padding:"1px 5px",letterSpacing:".08em"}}>P{ph}</span>
              <span style={{fontSize:13,fontWeight:900,color:phData.color}}>DAY {dayData.day}</span>
              <span style={{fontSize:11,fontWeight:700,color:"#555"}}>{dayData.label} — {dayData.sub}</span>
            </div>
            {Object.entries(exercises).map(([eid,sets])=>(
              <div key={eid} style={{padding:"8px 12px",borderBottom:"1px solid #161616"}}>
                <div style={{fontSize:11,fontWeight:700,color:"#BBB",marginBottom:5}}>{exMap[eid]||eid}</div>
                <div style={{display:"flex",gap:4,flexWrap:"wrap"}}>
                  {sets.sort((a,b)=>a.si-b.si).map((s,i)=>(
                    <div key={i} style={{background:"#181818",border:"1px solid #222",borderRadius:6,padding:"4px 8px",display:"flex",flexDirection:"column",alignItems:"center",gap:1,minWidth:48}}>
                      <span style={{fontSize:7.5,color:"#3A3A3A",fontWeight:700}}>SET {s.si+1}</span>
                      {s.weight&&<span style={{fontSize:12,fontWeight:800,color:"#C9A84C"}}>{s.weight}<span style={{fontSize:7,color:"#555"}}>lb</span></span>}
                      {s.reps&&<span style={{fontSize:10,fontWeight:700,color:"#7EB8D4"}}>{s.reps}<span style={{fontSize:7,color:"#555"}}>reps</span></span>}
                      {!s.weight&&!s.reps&&<span style={{fontSize:9,color:"#3A3A3A"}}>✓</span>}
                    </div>
                  ))}
                </div>
              </div>
            ))}
          </div>
        );
      })}
    </div>
  );
}

const root=ReactDOM.createRoot(document.getElementById('root'));
root.render(<App/>);
</script>
</body>
</html>
