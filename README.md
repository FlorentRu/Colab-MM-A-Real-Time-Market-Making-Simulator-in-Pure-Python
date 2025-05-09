# Colab MM A Real Time Market Making Simulator in Pure Python


In a controlled environment, this project allows us to watch a miniature, risk‑free version of what professional market‑makers do every millisecond on real exchanges: stream fresh quotes, store them in a time‑series database, run a machine‑learning model to decide a “fair” bid–ask spread, and then visualise everything as it happens. Because every component—data feed, message queue, storage, model and charts—runs in pure Python on free Colab hardware, we can explore latency‑sensitive trading ideas without installing servers or buying market data.

*Stream → Store → Predict → Visualize*  this notebook streams synthetic quote data, stores it in a kdb⁺‑style table, predicts optimal bid/ask spreads with **LightGBM**, and renders live Matplotlib dashboards.  
Beyond a coding demo, the project mirrors real‑world pipelines used by modern market‑makers, letting you prototype latency‑sensitive, analytics‑rich systems **without any production risk**.

---

## Real‑Life Benefits

| Benefit | Why It Matters |
|---------|----------------|
| **kdb⁺‑style storage** | Mirrors the time‑series database of choice on trading desks, enabling ultra‑fast tick analytics. |
| **Kafka‑pattern queue** | Reflects event‑driven architectures that handle millions of exchange messages per second. |
| **LightGBM model** | Fast to train, great on tabular features, ideal for intra‑day re‑tuning with minimal downtime. |
| **Runs in Virtual Environment** | GPUs, share‑by‑URL, no DevOps overhead. |
| **Thread‑safe design** | Shows real concurrency skills, critical for trading support software. |
| **Inline Matplotlib dashboards** | Zero‑latency visuals; no websockets required. |
| **Synthetic data generator** | Lets you test ideas without proprietary feeds or exchange fees. |
| **Market‑maker logic transparency** | Encapsulates liquidity‑provision economics for new hires and students. |
| **Interview‑ready demo** | Practically aligns with trading processes. |


producer_thread ──▶ queue.Queue ──▶ consumer_thread ──▶ quotes_df

                                                │
                             analytics_thread ◀─┘  (LightGBM prediction)

