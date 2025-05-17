# DevTwitter Dataset

[![Persian](https://img.shields.io/badge/Language-Persian-green)](README.md)
[![Programming](https://img.shields.io/badge/Topic-Programming-blue)](README.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

<p align="center">
  <a href="https://t.me/devtwitter"><img src="https://cdn.buymeacoffee.com/uploads/profile_pictures/2023/08/Pfi1BoIwIjiry8AU.jpg@300w_0e.webp" alt="DevTwitter Logo" width="200"/></a>
</p>

> A curated collection of programming-related posts from the DevTwitter Telegram channel

## 📖 Overview

This repository contains a JSON export of the public Telegram channel "DevTwitter | توییت برنامه نویسی", a Persian-language programming community. The dataset includes posts, links, and reactions from the channel since its creation in May 2020.

## 🚀 Features

- Complete message history from the channel's inception to May 16, 2025
- Rich content including text posts, links to programming articles, and images
- Reaction data showing community engagement
- Message timestamps and editing information
- Perfect for data analysis, NLP research, or content mining

## 📊 Dataset Structure

The dataset is provided as a single JSON file with the following high-level structure:

```json
{
  "name": "DevTwitter | توییت برنامه نویسی",
  "type": "public_channel",
  "id": 1377200663,
  "messages": [
    // Array of message objects
  ]
}
```

## 🔍 Use Cases

- **NLP Research**: Train models on Persian programming terminology
- **Content Analysis**: Study programming trends in the Persian developer community
- **Educational Resources**: Create collections of valuable programming resources
- **Recommendation Systems**: Build tools to suggest programming articles based on popularity

## 🧰 Getting Started

### Prerequisites

- Any JSON parser or programming language with JSON support

### Basic Usage

```python
# Python example
import json
from collections import Counter

# Load the dataset
with open('devtwitter-dataset.json', 'r', encoding='utf-8') as file:
    data = json.load(file)

# Count all messages
message_count = len(data['messages'])
print(f"Total messages: {message_count}")

# Get all links shared in the channel
links = []
for message in data['messages']:
    if 'text_entities' in message:
        for entity in message['text_entities']:
            if entity['type'] == 'link':
                links.append(entity['text'])

unique_links = list(set(links))
print(f"Total unique links: {len(unique_links)}")

# Analyze message frequency over time
from datetime import datetime
dates = [message['date'][:10] for message in data['messages'] if 'date' in message]
date_counter = Counter(dates)

print("Top 5 most active days:")
for date, count in date_counter.most_common(5):
    print(f"  {date}: {count} messages")

# Count reaction types
reactions = []
for message in data['messages']:
    if 'reactions' in message:
        for reaction in message['reactions']:
            reactions.extend([reaction['emoji']] * reaction['count'])

reaction_counter = Counter(reactions)
print("Top reactions:")
for emoji, count in reaction_counter.most_common(5):
    print(f"  {emoji}: {count}")
```

## 📈 Statistics

- **Total Messages**: 8K+
- **Date Range**: May 23, 2020 - May 16, 2025
- **Top Categories**: Web Development, DevOps, Programming Languages, Software Engineering
- **Languages**: Persian (Farsi), with English technical content

## 💖 Support DevTwitter

If you find this dataset useful or enjoy the content from the DevTwitter channel, please consider supporting us:

<p align="center">
  <a href="https://hamibash.com/devtwitter">
    <img src="https://img.shields.io/badge/Support_us_on-HamiBash-E44D26?style=for-the-badge" alt="Support on HamiBash"/>
  </a>
  &nbsp;&nbsp;
  <a href="https://buymeacoffee.com/devtwitter">
    <img src="https://img.shields.io/badge/Buy_me_a-Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me A Coffee"/>
  </a>
</p>

Your support helps us maintain the channel and continue sharing valuable programming content with the community.

## 📄 License

This dataset is released under the MIT License. See the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

This dataset contains publicly available information from a Telegram channel. All content belongs to their respective owners. This compilation is provided for educational and research purposes only.

## 🙏 Acknowledgements

- Thanks to all contributors of the DevTwitter Telegram channel
- Special thanks to the Persian developer community for sharing valuable programming knowledge

---

<p align="center">
  Made with ❤️ for the developer community
</p>
