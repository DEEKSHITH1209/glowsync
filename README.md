# GlowSync AI
> **B.Tech Major Project:** AI-Powered Skin Product Recommendation Using Deep Learning  
> **Tagline:** *Your Skin. Your Science. Your Glow. — Personalized Skincare, Powered by AI.*

---

## 🌿 Project Overview

**GlowSync AI** is a modern, responsive, production-quality skincare technology web application designed to help users understand their unique cutaneous characteristics and receive mathematically personalized skincare product recommendations.

The platform provides a dual assessment pipeline:
1. **AI Image Analysis:** Uses client-side camera capture (HTML5 WebRTC) or image upload with automated validation (aspect ratio, Laplacian illumination check), face ROI landmark detection, and deep learning classification (EfficientNetB0 for skin type, EfficientNetV2S for visible skin concerns, and YCbCr/HSV K-Means for Fitzpatrick skin tone estimation).
2. **Manual Skin Assessment:** An accessible, dermatologically structured questionnaire for users who prefer not to share a photo, collecting skin type, multiple concerns, sensitivity level, primary skincare objectives, and specific ingredients to avoid.

Recommendations are generated using **Content-Based Filtering with Cosine Similarity**, vectorizing user skin profiles against formulation active matrices.

---

## 🚀 Key Features Implemented

### 1. Landing Page (`/`)
- **Hero Section:** "Your Skin. Your Science. Your Glow." with call-to-action buttons, deep-learning badges, and facial landmark composition preview.
- **Three-Step Workflow:** 1. Capture/Input → 2. Deep Neural Classification → 3. Cosine Recommendation.
- **Capabilities Matrix:** Features covering CNN inference, multi-label detection, color-space decomposition, and barrier preservation.
- **Supported Skin Types & Concerns:** Interactive overview of Oily, Dry, Combination, Normal, Sensitive profiles and 8 key dermatological concerns.
- **Sample Catalog Preview:** Real skincare formulation cards with ratings and actives.
- **Technical Pipeline Architecture Card:** Documenting the 7-stage academic methodology.

### 2. Skin Analysis Studio (`/analysis`)
- **Dual-Mode Tabs:** Seamless switching between AI Image Analysis and Manual Assessment.
- **Camera Capture:** Direct browser camera stream using `navigator.mediaDevices.getUserMedia` with facial oval alignment guide, snapshot capture, and front/back camera switching.
- **File Uploader:** Drag-and-drop zone with JPEG/PNG/WebP validation, 10MB size checks, preview, replace, and remove controls.
- **Privacy Notice:** Clear disclosure highlighting zero biometric retention.
- **Multi-Stage Progress Indicator:** Real-time visual tracking of preprocessing, landmark extraction, EfficientNetB0 inference, EfficientNetV2S multi-label detection, and cosine similarity matching.
- **Manual Assessment Form:** Interactive selectors for skin type, multi-select concerns, sensitivity tiers, skincare goals, and ingredient avoidances.

### 3. Diagnostic Results Dashboard (`/results`)
- Inferred or declared primary skin type with model confidence percentage.
- Visible skin concerns breakdown with severity, affected region, and probability bars.
- Skin tone estimation mapped to Fitzpatrick phototypes (I to VI) with hex color swatches.
- **Interactive Facial ROI Overlay:** Toggleable visual bounding boxes showing detected T-zone, cheek texture, and erythema regions on the uploaded photo.
- Quick navigation to recommended products and morning/evening routines.
- Prominent dermatological safety disclaimer.

### 4. Personalized Recommendations (`/recommendations`)
- Content-based cosine similarity ranking for every product.
- Real skincare product catalog with active ingredients (Niacinamide, Salicylic Acid, Hyaluronic Acid, Ceramides, Centella, Retinol, Vitamin C, Zinc, Azelaic Acid).
- Category filtering: All, Cleanser, Toner, Serum, Moisturizer, Sunscreen, Treatment.
- Real-time search across product names, brands, and key actives.
- Sorting: Best Cosine Match, Highest Rating, Price (Low to High / High to Low).
- Cosine similarity mathematical explanation modal.
- "Add to Routine" and "Bookmark" quick actions.

### 5. Product Details Modal
- Full INCI ingredient list.
- Cosine recommendation rationale (why it matches the user's specific skin profile).
- Application protocol (AM / PM timing, sequence step).
- 24-hour patch test guidance and dermatological caution notes.

### 6. Personalized Skincare Routine (`/routine`)
- Structured into Morning (AM) and Evening (PM) regimens.
- Interactive step-by-step checklist with progress bar.
- Daily reset button to refresh checklist state.
- Biochemical safety rules (sunscreen requirement with actives, avoiding retinol/exfoliant overload).

### 7. Natural Remedies & Lifestyle Guidance (`/lifestyle`)
- Evidence-based lifestyle pillars: Hydration, UV photoprotection, sleep & circadian rhythms, antioxidant nutrition, and acid mantle preservation.
- Safe botanical remedies: Pure cold-pressed aloe vera, chilled green tea compresses, colloidal oatmeal.
- Critical warnings against harmful DIY internet trends (undiluted lemon juice, baking soda, toothpaste, walnut scrubs).
- Clear distinction between general lifestyle hygiene and medical dermatology.

### 8. User Profile & System Diagnostics (`/profile`)
- Local session storage with zero cloud tracking.
- Analysis history with ability to reactivate previous profiles or clear data.
- Saved / bookmarked formulations list.
- Backend connectivity diagnostics and toggle for demonstration mode.

---

## 🛠️ Technology Stack

- **Frontend:** React 19 (Functional Components, Custom Hooks)
- **Styling:** Tailwind CSS (v4) with custom botanical luxury theme tokens
- **Routing:** React Router v7 (`react-router-dom`)
- **Icons:** Lucide React (`lucide-react`)
- **Build Tool:** Vite 8 (Hot Module Replacement, optimized bundling)
- **Algorithms:**
  - Convolutional Neural Network heads: EfficientNetB0 (Type) & EfficientNetV2S (Concerns)
  - Colorimetric Analysis: YCbCr & HSV color decomposition + K-Means clustering
  - Recommendation Engine: Content-Based Filtering using Cosine Similarity

---

## 💻 Getting Started & Installation

### Prerequisites
- Node.js (v18 or newer recommended, verified on Node v24)
- npm (verified on npm 11/12)

### Installation
```bash
# Navigate to the project directory
cd glowsync-ai

# Install dependencies
npm install

# Start development server
npm run dev
```

The application will be accessible at:
```
http://localhost:5173/
```

### Production Build
```bash
npm run build
npm run preview
```

---

## 🔗 API Integration & Endpoints

The frontend uses a centralized API client module in `src/services/api.js` and `src/services/skinAnalysis.js`.

### Connected / Ready Endpoints:
- `GET /api/health` — Checks backend server connectivity status.
- `POST /api/analyze-skin` — Transmits `multipart/form-data` image to the deep learning model.
- `POST /api/manual-assessment` — Transmits structured JSON skin characteristics.
- `GET /api/recommendations` — Retrieves cosine-matched products from backend catalog.

*Note:* When a live backend server is not running, GlowSync AI automatically engages its **Calibrated Demonstration Engine**, allowing seamless presentation and grading without network failures.

---

## 🔒 Privacy & Safety Disclaimer

GlowSync AI was developed as an academic engineering demonstration. Facial images are processed ephemerally and never retained. Predictions are non-invasive approximations for cosmetic product formulation pairing and do not replace a qualified dermatologist or medical diagnosis.
