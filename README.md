# MRML — Memory Recall & Mapping Layer

## Purpose
The Memory Recall & Mapping Layer (MRML) defines how an autonomous agent retrieves, indexes, and maps memory structures during task execution.  
It ensures deterministic memory access, stable recall, and consistent interpretation of stored information.

MRML prevents:

- inconsistent memory retrieval  
- hallucinated recall  
- memory fragmentation  
- conflicting memory states  
- non‑deterministic lookup behavior  

This template is the memory backbone of the ecosystem.

---

## When to Use This Template
Use MRML when an agent must:

- recall stored information  
- map memory to current tasks  
- resolve conflicting memory entries  
- index new information deterministically  
- maintain long‑term state consistency  
- support multi‑agent shared memory environments  

MRML is required before using ERP (Error Recovery Protocol) and LFE (Long‑Form Execution).

---

## Inputs
The agent receives:

- memory query  
- memory type (short‑term, long‑term, shared, task‑bound)  
- context window  
- constraints  
- safety rules  
- agent’s ASP profile  
- consensus results from MACP  

---

## Outputs
MRML produces a **memory mapping packet**, including:

- retrieved memory entries  
- relevance scores  
- conflict resolution notes  
- memory lineage (origin, timestamp, agent source)  
- mapping to current task  
- safety or policy flags  

---

## JSON Schema (Machine‑Native)

```json
{
  "memory_mapping": {
    "query_id": "string",
    "query": "string",
    "memory_type": "short | long | shared | task",
    "context_window": ["string"],
    "retrieved_entries": [
      {
        "entry_id": "string",
        "content": "string",
        "timestamp": "string",
        "source_agent": "string",
        "relevance_score": "number"
      }
    ],
    "conflict_resolution": {
      "conflicts_detected": ["string"],
      "resolution_method": "priority | timestamp | consensus",
      "notes": "string"
    },
    "mapping": {
      "task_alignment": "string",
      "usage_recommendation": "string"
    },
    "policy_flags": ["string"]
  }
}


Example Usage
{
  "memory_mapping": {
    "query_id": "mem-882",
    "query": "preferred workflow mode",
    "memory_type": "long",
    "context_window": ["workflow-generation", "deterministic-mode"],
    "retrieved_entries": [
      {
        "entry_id": "e1",
        "content": "User prefers deterministic workflow generation.",
        "timestamp": "2026-04-20T10:00:00Z",
        "source_agent": "alpha-01",
        "relevance_score": 0.92
      }
    ],
    "conflict_resolution": {
      "conflicts_detected": [],
      "resolution_method": "priority",
      "notes": "No conflicting entries found."
    },
    "mapping": {
      "task_alignment": "Matches current workflow generation task.",
      "usage_recommendation": "Apply deterministic mode."
    },
    "policy_flags": []
  }
}

Integration Notes
MRML should be used after MACP finalizes consensus.

Memory retrieval must be deterministic and reproducible.

Relevance scoring should be stable across sessions.

MRML feeds directly into ERP (Error Recovery Protocol) and LFE (Long‑Form Execution).

Multi‑agent systems rely on MRML to maintain consistent shared memory states.

Payment (Short Version)
Payments accepted for this template:

BTC

XMR

LTC

ETH / USDT / USDC (ERC‑20)

SOL (USDT/USDC)

Delivery is fully automated and zero‑contact.

---

# ⭐ When you're ready  
Save this README into your **MRML** repo, then tell me:

**MRML saved**

I’ll verify it exactly like the others — and then we’ll move to:

### **Template #8 — ERP (Error Recovery Protocol)**
