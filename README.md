I like the idea of thinking beyond a "Twitter archive." If the goal is a **Pashto Multimodal Knowledge Corpus (PMKC)**, then Twitter becomes just **one source**. Later you can add YouTube, Facebook (where permitted), news websites, books, interviews, OCR documents, and speech data without changing the overall architecture.

A research corpus rather than a social media dump.

```text
Pashto-Multimodal-Knowledge-Corpus/
│
├── README.md
├── LICENSE
├── CITATION.cff
├── VERSION
├── CHANGELOG.md
│
├── docs/
│   ├── architecture.md
│   ├── data_model.md
│   ├── annotation_guidelines.md
│   ├── metadata_schema.md
│   ├── quality_control.md
│   ├── corpus_statistics.md
│   └── roadmap.md
│
├── schemas/
│   ├── tweet.schema.json
│   ├── image.schema.json
│   ├── video.schema.json
│   ├── document.schema.json
│   ├── audio.schema.json
│   ├── conversation.schema.json
│   └── knowledge_record.schema.json
│
├── sources/
│   ├── twitter/
│   ├── youtube/
│   ├── news/
│   ├── wikipedia/
│   ├── books/
│   ├── blogs/
│   ├── government/
│   ├── humanitarian/
│   └── custom/
│
├── corpus/
│   │
│   ├── raw/
│   │
│   ├── normalized/
│   │
│   ├── enriched/
│   │
│   ├── multilingual/
│   │
│   └── final/
│
├── media/
│   ├── images/
│   ├── videos/
│   ├── audio/
│   ├── thumbnails/
│   └── documents/
│
├── metadata/
│   ├── authors/
│   ├── locations/
│   ├── hashtags/
│   ├── organizations/
│   ├── events/
│   ├── languages/
│   └── topics/
│
├── knowledge/
│   ├── entities/
│   ├── relations/
│   ├── timelines/
│   ├── claims/
│   ├── evidence/
│   └── knowledge_graph/
│
├── annotations/
│   ├── image_caption/
│   ├── object_detection/
│   ├── ocr/
│   ├── translation/
│   ├── summarization/
│   ├── sentiment/
│   ├── stance/
│   ├── misinformation/
│   ├── geopolitics/
│   └── human_review/
│
├── embeddings/
│   ├── text/
│   ├── image/
│   ├── audio/
│   ├── multimodal/
│   └── indexes/
│
├── datasets/
│   ├── train/
│   ├── validation/
│   ├── test/
│   ├── instruction/
│   ├── vision_language/
│   ├── retrieval/
│   └── benchmark/
│
├── database/
│   ├── sqlite/
│   ├── duckdb/
│   ├── parquet/
│   ├── jsonl/
│   └── vector_db/
│
├── api/
│   ├── search/
│   ├── retrieval/
│   ├── rag/
│   ├── corpus_api/
│   └── web/
│
├── tools/
│   ├── collectors/
│   ├── converters/
│   ├── validators/
│   ├── deduplication/
│   ├── enrichment/
│   ├── exporters/
│   └── statistics/
│
├── experiments/
│
└── models/
    ├── checkpoints/
    ├── adapters/
    ├── prompts/
    └── evaluation/
```

---

# Recommended Knowledge Record

Every piece of information should eventually become one independent record.

```text
knowledge_record
│
├── id
├── source
├── language
├── created_at
├── collected_at
│
├── author
├── organization
├── location
│
├── text
├── translation
├── summary
│
├── images[]
├── videos[]
├── audio[]
├── documents[]
│
├── hashtags[]
├── urls[]
├── mentions[]
│
├── entities[]
├── events[]
├── topics[]
│
├── image_captions[]
├── ocr_text[]
│
├── embeddings
│
├── relationships
│
├── verification
│
└── licenses
```

---

# Twitter Source Layout

For Twitter specifically:

```text
sources/
└── twitter/
    ├── users/
    │   ├── user1/
    │   ├── user2/
    │   └── ...
    │
    ├── tweets/
    │   ├── raw_jsonl/
    │   ├── normalized/
    │   └── enriched/
    │
    ├── media/
    │   ├── images/
    │   ├── videos/
    │   └── thumbnails/
    │
    ├── conversations/
    │
    ├── quoted/
    │
    ├── replies/
    │
    └── indexes/
```

---

# Long-Term Vision

Instead of treating a tweet as "text + image," treat it as a **knowledge object**:

```
Knowledge Object

            Text
              │
              │
 Image ───────┼────── Metadata
              │
              │
     Time ────┼──── Author
              │
              │
 Conversation │
              │
         Entities
              │
              │
       Knowledge Graph
              │
              │
       Embeddings
              │
              │
          AI Retrieval
```

This design is scalable from thousands to tens of millions of records and is suitable for retrieval systems, multimodal model training, digital humanities research, and long-term preservation. It also aligns well with your broader work on Pashto language resources, making the corpus a central foundation that other datasets (dictionary, translation, OCR, speech, and instruction tuning) can connect to rather than remain isolated projects.
