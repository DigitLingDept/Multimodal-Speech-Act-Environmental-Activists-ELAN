# ELAN Multimodal Speech Act Annotation Scheme

This instruction set describes how to annotate spoken speeches in ELAN using both verbal and nonverbal tiers. The scheme consists of:

- A base transcript tier `Speech` segmented into speech-act units.
- Two verbal coding tiers: `Speech act` (illocutionary type) and `Rhetoric` (rhetorical appeal).
- Four nonverbal tiers: `Mimicry`, `Oculistics`, `Posture`, `Gesture`.
- One functional tier: `Non-verbal function` for gesture function labels.

The guide assumes basic familiarity with ELAN (creating projects, tiers, and annotations).

---

## 1. Verbal Segmentation and Coding

### 1.1 Create the base transcript tier

1. Open the video/audio in ELAN.
2. Create an alignable tier:

   - Tier name: `Speech`
   - Linguistic type: e.g. `Verbal` (time-alignable)

3. Paste or type the full transcript into this tier as time-aligned annotations.

   - Each annotation should cover one utterance that will later correspond to a single speech act.

### 1.2 Segment into speech acts

1. Play the media and locate meaningful units of talk.
2. Use a consistent segmentation criterion (e.g. predicate-finality / clause boundaries):

   - Each segment should represent a single illocutionary act (one main proposition or intention).

3. In ELAN, split or create annotations on `Speech` so that each annotation corresponds to one speech act.

### 1.3 Add speech act labels

1. Define a controlled vocabulary for speech acts, e.g.:

   - `assertive`
   - `directive`
   - `commissive`
   - `expressive`
   - `declarative`

2. Create an alignable tier:

   - Tier name: `Speech act`
   - Linguistic type: e.g. `Speech act`
   - Controlled vocabulary: the list above

3. For each `Speech` annotation:

   - Create a corresponding annotation on `Speech act` with the same time span.
   - Choose the appropriate speech act label from the controlled vocabulary.

### 1.4 Add rhetorical appeal labels

1. Define a controlled vocabulary for rhetorical types, e.g.:

   - `ethos`
   - `pathos`
   - `logos`

2. Create an alignable tier:

   - Tier name: `Rhetoric`
   - Linguistic type: e.g. `Rhetoric`
   - Controlled vocabulary: the list above

3. For each `Speech` annotation:

   - Create a corresponding annotation on `Rhetoric` with the same time span.
   - Choose the primary rhetorical appeal label for that segment.

### 1.5 Notes on flexibility

- You may replace Searle’s categories with any other speech act taxonomy.
- You may replace Aristotle’s triad with any other rhetorical framework.
- The structure (one label per segment on separate tiers) remains the same regardless of the specific framework.

---

## 2. Nonverbal Annotation

Create separate alignable tiers for each nonverbal channel. All of these tiers are time-aligned to the video and to `Speech`.

### 2.1 Mimicry (facial expression)

1. Create an alignable tier:

   - Tier name: `Mimicry`
   - Linguistic type: e.g. `Non-verbal`

2. While playing the video, annotate facial expressions:

   - Each annotation covers the time interval where a distinct expression is present.
   - Use short descriptions such as:
     - `neutral face`
     - `slight smile`
     - `furrowed brows`
     - `focused expression`

3. Reuse descriptive terms consistently across the corpus.

### 2.2 Oculistics (eye gaze)

1. Create an alignable tier:

   - Tier name: `Oculistics`
   - Linguistic type: e.g. `Non-verbal`

2. Annotate gaze behavior:

   - `direct gaze toward audience`
   - `gaze down at notes`
   - `gaze to left/right`
   - `scanning the audience`

3. Each annotation spans the period where that gaze behavior holds.

### 2.3 Posture

1. Create an alignable tier:

   - Tier name: `Posture`
   - Linguistic type: e.g. `Non-verbal`

2. Annotate notable postural configurations or changes:

   - `upright stance`
   - `slight forward lean`
   - `hand on hip`
   - `leaning over podium`

3. Use one annotation per stable posture segment.

### 2.4 Gesture (manual gestures)

1. Create an alignable tier:

   - Tier name: `Gesture`
   - Linguistic type: e.g. `Non-verbal`

2. Annotate intentional hand/arm movements:

   - `broad arm movement`
   - `pointing gesture`
   - `fist raised`
   - `counting gesture with fingers`

3. Do not code small, incidental movements; focus on clearly communicative gestures.

4. Each gesture is one annotation spanning from onset to offset.

### 2.5 Gesture function

1. Define a controlled vocabulary for gesture functions, e.g.:

   - `discourse structuring`
   - `pragmatic`
   - `thought-formulating`
   - `representational: object-referencing`
   - `representational: action-referencing`

2. Create an alignable tier:

   - Tier name: `Non-verbal function`
   - Linguistic type: e.g. `Non-verbal function`
   - Controlled vocabulary: list above

3. For each annotation on `Gesture`:

   - Create a corresponding annotation on `Non-verbal function` with the same time span.
   - Assign exactly one function label from the controlled vocabulary.

4. Example interpretations:

   - `discourse structuring` – organizing discourse (e.g. listing points with fingers).
   - `pragmatic` – emphasizing or regulating interaction (beats, pointing).
   - `thought-formulating` – gestures accompanying visible planning or searching for words.
   - `representational: object-referencing` – gestures depicting objects or spatial layouts.
   - `representational: action-referencing` – gestures depicting actions or processes.

### 2.6 Controlled vocabularies for nonverbal tiers (optional)

- In this scheme, `Mimicry`, `Oculistics`, and `Posture` use free-text descriptions.
- For more rigorous analysis:

  - Define controlled vocabularies for facial expressions, gaze types, and posture categories.
  - Link these CVs to their respective tiers in ELAN.
  - Use fixed codes instead of free-text.

---

## 3. Tier Hierarchy and Alignment

### 3.1 Base alignment

- `Speech` is the primary alignable tier containing segmented utterances.
- All other tiers reference the same media time axis.

### 3.2 Parallel verbal tiers

- `Speech act` annotations match the time boundaries of `Speech` segments.
- `Rhetoric` annotations also match the time boundaries of `Speech`.

This yields, for each segment:

- One transcript (on `Speech`).
- One speech-act label (on `Speech act`).
- One rhetorical label (on `Rhetoric`).

### 3.3 Nonverbal tiers

- `Mimicry`, `Oculistics`, `Posture`, and `Gesture` are alignable tiers:

  - Their annotations are placed wherever a nonverbal event occurs.
  - They may overlap in time with multiple speech segments or with each other.

- `Non-verbal function` is linked to `Gesture`:

  - Each gesture has exactly one function annotation with matching time span.

### 3.4 Overlaps

- Nonverbal annotations may overlap:

  - A single gesture can span multiple speech segments.
  - Multiple nonverbal channels (e.g. facial expression and gesture) can be active simultaneously.

- ELAN supports overlapping annotations on different tiers; no special handling is required beyond consistent time alignment.

---

## 4. Adapting the Scheme

### 4.1 Alternative verbal frameworks

- Replace Searle’s categories with any other speech-act taxonomy.
- Replace ethos/pathos/logos with any other rhetorical or functional classification.
- Keep tier structure:

  - One tier for speech act / function of utterance.
  - One tier for rhetorical or other discourse-level category.

### 4.2 Extending or simplifying nonverbal tiers

- You may:

  - Merge `Mimicry` and `Oculistics` into a single `Face/Gaze` tier.
  - Split `Gesture` into multiple tiers (e.g. `Left hand`, `Right hand`) if needed.
  - Add new tiers (e.g. `Prosody`, `Head movement`) with the same principles.

- For rigorous projects:

  - Define controlled vocabularies for all nonverbal tiers.
  - Document codes and their definitions in a separate codebook.

### 4.3 Multi-speaker data

- For multiple speakers:

  - Duplicate the tier set for each participant.
  - Assign each tier to the appropriate participant in ELAN.

- Keep tier names consistent, but distinguish participant via the `Participant` field.

---

## 5. Hybrid Use in Larger Projects

- One or several speeches can be fully annotated with the full tier set described above.
- Remaining speeches can be:

  - Coded manually following the same definitions, or
  - Annotated in a simplified tier set for efficiency.

- The fully annotated ELAN file(s) serve as:

  - A reference implementation of the scheme.
  - A training resource for annotators.
  - A transparency artifact for methodological documentation.

By following this guide, researchers can replicate the multimodal annotation scheme or adapt it to their own speech data and analytic frameworks.