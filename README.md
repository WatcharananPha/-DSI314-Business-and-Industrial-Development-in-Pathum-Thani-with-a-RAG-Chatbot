# **Business and Industrial Development in Pathum-Thani with a Chatbot**


This guide provides step-by-step instructions to set up the required environment and install necessary packages for this project.

---

## Prerequisites
Ensure you have Python 3.11 installed on your machine.

---

## Environment Setup

1. Create a virtual environment named `DSI314`:
   ```bash
   python3.11 -m venv DSI314

2. Verify the Python version :
   ```bash
   python --version

3. Activate the virtual environment :
   ```bash
   .\DSI314\Scripts\activate

4. Confirm the virtual environment files are created :
   ```bash
   ls

## Install Required Packages 
1. Check for the `requirements.txt` file in the project folder.
Ensure it is present before proceeding.

2. Activate the virtual environment :
   ```bash
   .\DSI314\Scripts\activate

3. Install dependencies from the `requirements.txt` file :
   ```bash
   pip install -r requirements.txt

## **Development Tools and Libraries**

### PDF to Text Conversion
- **[LlamaIndex Parse](https://cloud.llamaindex.ai/landing) :** PDF ที่มีโครงสร้างซับซ้อน ใช้สำหรับการดึง text จาก PDF โดยเฉพาะใน file ที่มี format เป็นตารางหรือกราฟจะทำได้ดี convert text ที่ extract ออกมาแล้วเป็น MD ที่มี structure

### Embedding Model
- **[BAAI/bge-m3](https://huggingface.co/BAAI/bge-m3) :** รองรับภาษาไทย (th) โดยสามารถทำงานแบบ Multi-Functionality คือ Dense, Sparse และ Colbert Retrievals ได้ในโมเดลเดียว รองรับความยาวของ Document สูงสุด 8192 tokens สามารถนำไปใช้กับ Re-ranking models ได้อย่างมีประสิทธิภาพ ช่วยเพิ่มความแม่นยำในการเลือกข้อมูลที่เกี่ยวข้องเพื่อนำมาสร้างคำตอบ

### Vector Database
- **[FAISS](https://github.com/facebookresearch/faiss) :** เป็นไลบรารีที่พัฒนาโดย Facebook AI Research เป็นเครื่องมือสำหรับทำงานด้าน similarity search และ clustering dense vectors โดยมีข้อดีคือทำ Vector Indexing and Searching เช่น flat (brute-force), inverted file, และ hierarchical navigable small world (HNSW) รองรับ CPU และ GPU สำหรับ accelerate the indexing and searching process สามารถสร้าง Semantic Cache ระหว่าง user’s question and the required data เพื่อลดเวลาในการ retrieval ข้อมูลได้มากถึง 95% และจะ store search results ไว้ เพื่อนำกลับมาใช้ใหม่ได้ หากมีคำถามที่คล้ายคลึงกันในภายหลัง

### LLM Generation Model
- **[typhoon-v1.5x-70b-instruct](https://opentyphoon.ai/app/api-key) :** มี Performance ใกล้เคียงกับ GPT-4-0612 ในภาษาไทย เนื่องจาก Fine tune บน Dataset ที่เป็นภาษาไทย  optimized for application use cases, Retrieval-Augmented Generation (RAG), constrained generation, and reasoning tasks ใช้เทคนิค Cross-lingual Transfer เข้ากับ Llama 3 Instruct ทำให้ได้โมเดลที่ทั้งเข้าใจภาษาไทยและตอบสนองต่อคำสั่งได้ดี

### **High level design for development**


<p align="center">
  <img src="https://drive.google.com/uc?id=1cy4XQjHZfZ4xF1WWLyJbcL2oneiztAKM" alt="Workflow" style="width:500px;" />
</p>

