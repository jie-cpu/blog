```
┌─────────────────────────────────────────────────────────────────┐
│  STEP 1: Brain Data Input                                       │
│                                                                 │
│  Your fMRI brain scan contains:                                 │
│  • How active each voxel is (signal strength, e.g., 0.8)        │
│  • Where the voxel is located (e.g., x=10, y=20, z=30)          │
│  • Which brain region it belongs to (e.g., V1 visual area,      │
│    MT motion area, FFA face area)                               │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────┐
│  STEP 2: Model "Looks at" Brain & Extracts Information          │
│                                                                 │
│  MindLLM internally performs an "attention" calculation:        │
│                                                                 │
│  • The model has hundreds of "query templates," like:           │
│    → "Which brain region recognizes faces?"                     │
│    → "Which brain region detects motion?"                       │
│                                                                 │
│  • Each query scans all voxels and calculates similarity:       │
│    → If voxel location matches + signal is strong → high weight│
│    → If location doesn't match → low weight                     │
│                                                                 │
│  • Finally, everything is compressed into one "Brain Vector"    │
│    (Brain Embedding)                                            │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────┐
│  STEP 3: Language Model Generates Text                          │
│                                                                 │
│  Brain Vector → Input to LLaMA / GPT → Generates word by word   │
│                                                                 │
│  Input: Brain Vector + "Describe what you see:"                 │
│  Output: "A person is opening a door" → "...entering a room"    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```