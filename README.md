```mermaid
graph TD
    subgraph GRU_Layer
        A[Input Sequence x_t] -->|Input| B[GRU Layer]
        B --> C[Hidden State h_t]
    end
    
    subgraph Attention_Mechanism
        C --> D[Repeated Hidden State h_t]
        E[Encoder Outputs h_j] --> F[Linear Transform W_a]
        D --> G[Concatenation [h_t; h_j]]
        G --> H[Calculate Attention Energy e_{tj}]
        H --> I[Softmax Normalization alpha_{tj}]
        I --> J[Compute Context Vector c_t]
    end
    
    J --> K[Fully Connected Layer FC]
    K --> L[Output Probability Distribution]

    style GRU_Layer fill:#f9f,stroke:#333,stroke-width:4px
    style Attention_Mechanism fill:#ff9,stroke:#333,stroke-width:4px
