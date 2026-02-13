# System Design: CreatorSahayak

## 1. High-Level Architecture
The system follows a simple Client-Server architecture powered by Generative AI APIs.

[User Interface (Streamlit)] <--> [Backend API (Python)] <--> [Gemini API / Google Cloud]

## 2. Data Flow
1.  **Input:** User selects a language (e.g., Hindi) and enters a topic (e.g., "How to make tea").
2.  **Processing:**
    * The backend sends a prompt to **Gemini Pro**: *"Write a 60-second YouTube Shorts script in Hindi about making tea. Keep it funny."*
    * Gemini Pro returns the text script.
    * Parallelly, the backend requests **SEO tags** based on the topic.
3.  **Output:** The UI displays the Script, Title Options, and Hashtags.

## 3. Module Description
### A. User Interface (UI)
* **Input Field:** Topic text box.
* **Language Dropdown:** Hindi, English, Gujarati, Marathi, Tamil.
* **Tone Selector:** Funny, Educational, Serious.
* **Generate Button:** Triggers the API calls.

### B. AI Engine
* **Script Module:** Uses LLM few-shot prompting to ensure cultural relevance (e.g., using Indian idioms).
* **Thumbnail Module:** Generates a text-to-image prompt like: *"A cinematic shot of a steaming cup of masala chai, sunset background, 4k resolution, text overlay: 'Best Chai!'"*

## 4. User Experience (UX)
* **Simplicity:** Minimalist design focusing on "One Click Generation".
* **Speed:** Results generated in under 10 seconds.
* **Mobile-First:** Designed for creators who work primarily from smartphones.

## 5. Future Scalability
* Integration with YouTube Data API to auto-upload videos.
* Voice-to-Text input for creators who prefer speaking over typing.
* AI Video editing integration using tools like Google Veo.
