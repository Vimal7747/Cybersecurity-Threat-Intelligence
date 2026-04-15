# Dataset Information

## CIC-IDS2018 (UNB Intrusion Detection System Dataset 2018)

The dataset used in this project is the **CIC-IDS2018** published by the 
Canadian Institute for Cybersecurity at the University of New Brunswick.

### Why it's not included here

The full dataset is approximately **336 MB** and exceeds GitHub's file size limits.

### How to Download

1. Visit: [https://www.unb.ca/cic/datasets/ids-2018.html](https://www.unb.ca/cic/datasets/ids-2018.html)
2. Register/request access if required
3. Download the CSV version of the dataset
4. Place the file in this `data/` folder and rename it to `CIC-IDS2018.csv`

### Dataset Properties

| Property | Value |
|---|---|
| Rows | 1,048,575 |
| Features | 80 |
| Target Column | `Label` |
| Classes | Benign, Bot |
| File Size | ~336 MB |

### Feature Categories

The dataset contains network flow features including:

- **Packet statistics** — lengths, counts, inter-arrival times
- **Flow metadata** — duration, bytes/second, packets/second
- **Flag counts** — SYN, ACK, FIN, RST, PSH, URG flags
- **Port & protocol info** — source/destination ports, protocol type
- **Active/idle times** — mean, std, max, min
- **Subflow features** — forward and backward subflow stats

### Class Distribution (Before SMOTE)

| Label | Count | % |
|---|---|---|
| Benign | ~700,000 | ~70% |
| Bot | ~286,000 | ~28% |
| Other | ~62,000 | ~2% |

> Note: This project uses a filtered subset focusing on Benign vs Bot classification.
> After SMOTE balancing: **608,644 samples per class**.

### Reference

> Sharafaldin, I., Habibi Lashkari, A., and Ghorbani, A. A. (2018).  
> *Toward Generating a New Intrusion Detection Dataset and Intrusion Traffic Characterization.*  
> 4th International Conference on Information Systems Security and Privacy (ICISSP).
