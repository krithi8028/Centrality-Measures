# SOCIAL NETWORK ANALYSIS
### CENTRALITY MEASURES

## DATASET DESCRIPTION

### Dataset 1: Condensed Matter Collaboration Network

This dataset represents scientific collaborations between authors who have co-authored research papers in the Condensed Matter (COND-MAT) category on arXiv. The dataset spans from January 1993 to April 2003 (a period of 124 months) and captures how authors collaborate over time. It is structured as an undirected network, meaning that an edge between two authors indicates mutual collaboration.

- **Nodes (Authors):**
  - Each node represents an author who has published at least one paper in the Condensed Matter section of arXiv.
  
- **Edges (Collaborations):**
  - If two authors ‘i’ and ‘j’ co-authored a paper, an undirected edge connects them.
  - If a paper has k authors, it forms a fully connected subgraph (a clique) with k(k-1)/2 edges.

### Data Format
- **FromNodeId** – ID of an author
- **ToNodeId** – ID of an author

The presence of an edge means these two authors co-authored at least one paper together.

### Dataset Statistics
| Property                          | Value       |
|-----------------------------------|-------------|
| Total Nodes (Authors)             | 23,133      |
| Total Edges (Collaborations)      | 93,497      |
| Nodes in Largest WCC              | 21,363 (92.3%) |
| Edges in Largest WCC              | 91,342 (97.7%) |
| Nodes in Largest SCC              | 21,363 (92.3%) |
| Edges in Largest SCC              | 91,342 (97.7%) |
| Average Clustering Coefficient     | 0.6334      |
| Number of Triangles                | 173,361     |
| Fraction of Closed Triangles       | 0.107       |
| Diameter (Longest Shortest Path)   | 14          |
| 90% Effective Diameter             | 6.5        |

### Data Characteristics
- **Undirected Graph:**
  - Collaboration is mutual.
  - If A co-authored a paper with B, both are connected.
  
- **High Clustering:**
  - The average clustering coefficient (0.6334) shows that authors tend to collaborate in tight groups.
  
- **Small-World Property:**
  - The diameter of 14 means that any two authors are connected by at most 14 steps.
  - The 90% effective diameter of 6.5 indicates most authors are much closer.

### Potential Use Case
(a) **Collaboration Network Analysis**
- Identifying influential researchers.
- Finding central figures in scientific communities.

(b) **Community Detection**
- Discovering research clusters (who frequently works together).

(c) **Co-authorship Prediction**
- Predicting future collaborations.

(d) **Network Evolution**
- Analysing how scientific collaborations grow over time.

### Dataset 2: College Message Network

This dataset represents private message exchanges between users in an online social network at the University of California, Irvine. It captures user interactions over time, showing who communicated with whom and when. The dataset is structured as a temporal directed network, meaning each interaction has a direction (sender → receiver) and a timestamp. The dataset is designed for social network analysis and has been formatted for use in SNAP (Stanford Network Analysis Platform), a widely used framework for analysing large-scale networks.

- **Nodes (Users):**
  - Each node represents a unique user in the online social network.
  - Users could search for others on the platform and initiate private conversations.
  - Since this is a social network, users likely had profiles, and interactions could be based on shared interests.

- **Edges (Messages):**
  - Each edge (u, v, t) represents a directed interaction, meaning:
    - User u sent a message to user v at time t (recorded as a Unix timestamp).
  - Since the edges are directed, the network is asymmetric, meaning:
    - If u sends a message to v, it does not mean v responded.
  - The presence of timestamps makes this a temporal network, enabling the study of interaction patterns over time.

### Data Format
- **FromNodeId** – ID of a user
- **ToNodeId** – ID of a user

The presence of an edge means these two users exchanged at least one message together.

### Data Statistics
| Property                          | Value       |
|-----------------------------------|-------------|
| Total Nodes (Users)               | 1,899       |
| Total Temporal Edges (Messages)   | 59,835      |
| Edges in Static Graph              | 20,296      |
| Time Span                          | 193 days    |

- **Nodes (1,899):**
  - There are 1,899 distinct users who participated in at least one conversation.

- **Temporal Edges (59,835):**
  - The dataset records 59,835 unique private messages over the 193-day period.

- **Edges in Static Graph (20,296):**
  - If we ignore timestamps, the dataset contains 20,296 unique interactions.
  - This means some users exchanged multiple messages over time.

- **Time Span (193 days):**
  - The dataset covers roughly 6 months, meaning we can analyse:
    - How messaging patterns evolve.
    - When users are most active.
    - How long conversations last.

### Dataset Characteristics
- **Directed Graph:**
  - The network is not symmetric.
  - If A sends a message to B, it does not mean B responded.

- **Temporal Structure:**
  - Since each message has a timestamp, we can analyse activity trends.
  - We can track peak usage times and response patterns.

- **Repeated Interactions:**
  - If multiple edges exist between the same pair of nodes, we can analyse conversational intensity.

- **Sparse Graph:**
  - With 1,899 nodes but only 20,296 unique edges (ignoring timestamps), the network is not fully connected.
  - Some users may have sent messages to only a few others.

### Potential Use Case
(a) **Social Network Analysis**
- Identifying influential users based on message activity.
- Finding message patterns (who interacts with whom).

(b) **Community Detection**
- Identifying closely connected user groups.
- Detecting friend circles or communication clusters.

(c) **Temporal Analysis**
- Understanding how user activity changes over days, weeks, or months.
- Analysing response times (how quickly users reply to messages).

(d) **Network Evolution**
- Studying user engagement trends over time.
- Predicting whether new users will engage based on past behaviour.

## CENTRALITY MEASURES 

### QUESTION: 
In the dataset, present the centrality measures you found (with top 10 as table and the visualisation for the distribution of the centrality measures for the complete network)  

#### Top 10 Nodes for Degree Centrality:
| Node   | Degree Centrality |
|--------|-------------------|
| 73647  | 0.012148          |
| 52658  | 0.010980          |
| 78667  | 0.008689          |
| 97632  | 0.008214          |
| 22987  | 0.007868          |
| 101425 | 0.007219          |
| 97788  | 0.006830          |
| 15439  | 0.006398          |
| 46269  | 0.006139          |
| 45942  | 0.006052          |

#### Top 10 Nodes for Eigenvector Centrality:
| Node   | Eigenvector Centrality |
|--------|------------------------|
| 22987  | 0.224976               |
| 97632  | 0.217068               |
| 87484  | 0.166880               |
| 52658  | 0.163823               |
| 45810  | 0.138883               |
| 64428  | 0.138137               |
| 25209  | 0.115676               |
| 95940  | 0.113887               |
| 80199  | 0.113190               |
| 18871  | 0.106227               |

#### Top 10 Nodes for Katz Centrality:
| Node   | Katz Centrality |
|--------|------------------|
| 52658  | 0.029197         |
| 73647  | 0.029050         |
| 97632  | 0.024385         |
| 22987  | 0.023699         |
| 78667  | 0.023367         |
| 101425 | 0.020444         |
| 15439  | 0.020017         |
| 97788  | 0.019519         |
| 46269  | 0.018958         |
| 45942  | 0.018707         |

#### Top 10 Nodes for PageRank Centrality:
| Node   | PageRank Centrality |
|--------|---------------------|
| 73647  | 0.001089            |
| 52658  | 0.000748            |
| 78667  | 0.000557            |
| 91392  | 0.000549            |
| 101425 | 0.000547            |
| 101355 | 0.000506            |
| 22757  | 0.000501            |
| 46269  | 0.000495            |
| 84209  | 0.000478            |
| 46016  | 0.000465            |

#### Top 10 Nodes for Betweenness Centrality:
| Node   | Betweenness Centrality |
|--------|------------------------|
| 73647  | 0.075806               |
| 52658  | 0.023939               |
| 101355 | 0.020840               |
| 22757  | 0.019115               |
| 101425 | 0.018933               |
| 46269  | 0.016858               |
| 78667  | 0.016229               |
| 46016  | 0.013269               |
| 56672  | 0.013045               |
| 15439  | 0.012092               |

#### Top 10 Nodes for Closeness Centrality:
| Node   | Closeness Centrality |
|--------|----------------------|
| 73647  | 0.275673             |
| 52658  | 0.263468             |
| 46269  | 0.260277             |
| 15439  | 0.256510             |
| 46016  | 0.254765             |
| 101425 | 0.254272             |
| 101355 | 0.254039             |
| 97632  | 0.252063             |
| 45942  | 0.250529             |
| 22757  | 0.248792             |

![image](https://github.com/user-attachments/assets/5408c517-9309-41d0-86ea-257fe481dbe2)


### CLUSTERING COEFFICIENT:
#### Local Clustering Coefficient 
##### Top 10 Nodes for Local Clustering Coefficient:
| Node   | Local Clustering Coefficient |
|--------|------------------------------|
| 11894  | 1.0                          |
| 94     | 1.0                          |
| 46745  | 1.0                          |
| 67665  | 1.0                          |
| 5489   | 1.0                          |
| 38677  | 1.0                          |
| 89659  | 1.0                          |
| 44830  | 1.0                          |
| 46918  | 1.0                          |
| 61080  | 1.0                          |

![image](https://github.com/user-attachments/assets/f2a8dedf-308b-4b41-9f5c-e2b9b43fda15)


## 1. College Message Network (Temporal, Directed Graph)
This dataset represents private message exchanges in an online university network, meaning we care about who is influential, who connects different groups, and how efficiently messages spread.

### Selected Centrality Measures
1. **PageRank Centrality** 
   - In social networks, influence is often measured by how many important users interact with a given user.
   - Since PageRank considers both the number of messages received and the importance of senders, it effectively identifies key users.

2. **Betweenness Centrality** 
   - Since users act as message relays, some individuals may connect separate user groups by bridging conversations.
   - Betweenness centrality highlights gatekeepers in message flow, crucial in understanding bottlenecks or information flow constraints.

3. **Closeness Centrality** 
   - Measures how quickly a user can reach all others in the network.
   - Since this dataset involves message exchange, knowing who can spread messages efficiently is useful for studying communication reachability and effectiveness.

### Why Other Centrality Measures Are Less Important?
- **Degree Centrality** → Measures the number of direct connections but ignores interaction frequency and influence, which are captured better by PageRank.
- **Eigenvector Centrality** → Works well in static networks (like research collaborations) but less meaningful in a message network with time-dependent interactions.
- **Katz Centrality** → Includes distance-based influence but is computationally expensive and not necessarily better than PageRank for this case.
- **Local Clustering Coefficient** → Measures how well a user’s connections are connected but does not help in identifying influence or communication patterns.

---

## 2. Condensed Matter Collaboration Network (Undirected, Static Graph)
This dataset represents scientific co-authorship, meaning we care about influential researchers, cross-disciplinary connectors, and group structures.

### Selected Centrality Measures
1. **Eigenvector Centrality** 
   - Unlike a social network, academic collaboration is prestige-driven—authors who work with highly reputed researchers gain influence.
   - Eigenvector centrality captures this by measuring how influential a researcher’s co-authors are.

2. **Betweenness Centrality** 
   - Some researchers bridge different research domains by collaborating across fields.
   - Betweenness centrality helps detect interdisciplinary researchers and collaboration hubs.

3. **Clustering Coefficient** 
   - Since research collaborations naturally form tight-knit communities, measuring clustering helps identify research groups and collaboration density.
   - A high clustering coefficient indicates a strongly connected field, while a lower one suggests interdisciplinary work.

### Why Other Centrality Measures Are Less Important?
- **PageRank Centrality** → Unlike social networks, research collaboration does not have a directed or recursive influence flow.
- **Degree Centrality** → Simply counting collaborations is not enough; influence matters more (better captured by Eigenvector).
- **Closeness Centrality** → Distance to other researchers is not as useful because the network is already highly connected.
- **Katz Centrality** → Similar to Eigenvector but less relevant for undirected networks.

---

## GENERAL INFERENCE
### College Message Network (Directed, Temporal) – Communication Dynamics & Influence
This network represents private message exchanges among students, making it useful for understanding information flow, influence, and communication bottlenecks.

#### Key Findings:
- Certain individuals dominate the network in terms of influence, acting as hubs for information spread (PageRank Centrality).
- Bridging nodes (high betweenness centrality) play a crucial role in connecting different student groups, making them important for inter-group communication.
- The network is dynamic, meaning influence can shift over time as communication patterns change.
- Users with high closeness centrality can efficiently reach most of the network, enabling fast information diffusion.

This study helps identify key communicators, gatekeepers, and information flow efficiency in a structured social system. The findings are useful for understanding engagement patterns, optimizing communication strategies, and detecting influential users in a digital or social platform.

---

### Condensed Matter Collaboration Network (Undirected, Static) – Scientific Influence & Research Connectivity
This network represents co-authorship relationships, making it valuable for analyzing influential researchers, collaboration trends, and academic impact.

#### Key Findings:
- Influential researchers (high eigenvector centrality) have strong ties with other influential figures, indicating high academic reputation.
- Some researchers bridge different research communities (high betweenness centrality), fostering interdisciplinary collaborations.
- The network exhibits strong clustering, meaning researchers tend to form tight-knit collaboration groups.
- Research hubs exist where multiple high-centrality nodes collaborate, driving innovation and scientific output.

This study helps uncover key academic influencers, collaboration structures, and interdisciplinary linkages. The insights can be used to identify leading researchers, promote collaborative opportunities, and understand the evolution of scientific research networks.

