# Multilingual Meeting GenAI Agent

A multilingual meeting assistant that uses generative AI to automatically extract key information, action items, and provide translations from meeting transcripts.

Kaggle Notebook: [Kaggle Notebook](https://www.kaggle.com/code/hellomomiji/capstone-project-gen-ai-intensive-course-2025q1)

Github: [Github Repository](https://github.com/hellomomiji/multilingual-meeting-genai-agent)

Blog Post: [https://hellomomiji.github.io/en/posts/2025-04-15-meeting-genai-agent/](https://hellomomiji.github.io/en/posts/2025-04-15-meeting-genai-agent/)

## Overview
This agent is an intelligent agent built with LangGraph and Google's Gemini model that transforms raw meeting transcripts into structured, actionable information. It can:

- Extract meeting titles and generate concise summaries
- Identify key discussion points
- Extract and organize action items with assignees and deadlines
- Translate all content into multiple languages
- Provide consistent, structured JSON outputs

## Gen AI Capabilities
This project showcases several advanced generative AI capabilities:

- Structured Output/JSON Mode: Generates consistently formatted outputs with defined schemas
- Few-Shot Prompting: Uses example meetings to guide the model
- Agents: Implements a multi-step workflow with specialized components
- Function Calling: Leverages tool functions for specific capabilities
- Document Understanding: Analyzes meeting transcripts to extract meaningful information

## Usage
```python
# Process a meeting transcript with translations
test_meeting_agent(
    transcript=test_transcript, # str, your raw text transcript
    should_translate=True, # bool, with or without translation
    target_languages=["Chinese", "Japanese"] # List[str], list of target languages to translate
)
```
## Architecture

The system uses a directed graph pattern with LangGraph:

- Summary Generation: Extracts title, summary, and key points
- Action Item Extraction: Identifies tasks, assignees, and deadlines
- Multilingual Translation: Translates content into requested languages

![graph](https://github.com/hellomomiji/hellomomiji.github.io/blob/main/static/images/meeting-genai-agent/graph.png)


## Requirements

- Python 3.8+
- LangChain
- LangGraph
- Google Generative AI API access

## Future Improvements
- Real-time meeting processing
- Integration with task management systems
- Enhanced speaker identification
- Conflict detection for overlapping action items
- Connections with company knowledge bases
- ...

## Owner
Yang Jiang (Momiji) | [Linkedin](https://www.linkedin.com/in/yang-jiang-koyo)

## License
MIT

## Example Output
```
==================================================
MEETING TITLE: Q2 Global Strategy Executive Meeting
==================================================

SUMMARY:
The Q2 Global Strategy Executive Meeting addressed successes in revenue and customer satisfaction, but also identified operational strains, particularly in Asia, including warehousing delays, software integration issues, and shipping delays. Teams were assigned action items to address these issues and prepare for a cross-team review in two weeks.

KEY POINTS:
1. Eastern China experiencing warehousing delays due to incompatible supplier software.
2. Marketing rollout in Southeast Asia delayed due to poor translation quality; localization needs improvement.
3. Japan market showing positive feedback for new product line, but facing shipping delays.
4. AI personalization prototype completed, but needs improved stability before a potential board demo.
5. China team negotiating partnerships with two major e-commerce platforms and considering a new distribution center in Shenzhen.

ACTION ITEMS:
1. Prepare a roadmap for cross-regional logistics improvement (Assigned to: US team, Due: In two weeks)
2. Outline integration resource needs (Assigned to: China team, Due: In two weeks)
3. Finalize e-commerce partnerships (Assigned to: China team, Due: Next quarter)
4. Submit support staffing plan (Assigned to: Japan team, Due: In two weeks)
5. Submit performance benchmarks for the AI prototype (Assigned to: Japan team, Due: In two weeks)

==================================================
TRANSLATIONS
==================================================

--- Chinese ---
TITLE: 第二季度全球战略执行会议
SUMMARY: 第二季度全球战略执行会议讨论了在收入和客户满意度方面的成功，同时也发现了运营压力，尤其是在亚洲地区，包括仓储延误、软件集成问题和运输延误。各团队被分配了行动项目以解决这些问题，并准备在两周内进行跨团队审查。

KEY POINTS:
1. 华东地区由于供应商软件不兼容，出现仓储延误。
2. 由于翻译质量不佳，东南亚地区的市场推广延迟；本地化需要改进。
3. 日本市场对新产品线表现出积极的反馈，但面临运输延误。
4. AI 个性化原型已完成，但在潜在的董事会演示之前，需要提高稳定性。
5. 中国团队正在与两家主要的电子商务平台谈判合作关系，并考虑在深圳建立一个新的配送中心。

ACTION ITEMS:
1. 准备一份跨区域物流改进路线图 (Assigned to: US team, Due: In two weeks)
2. 概述集成资源需求 (Assigned to: China team, Due: In two weeks)
3. 完成电子商务合作伙伴关系 (Assigned to: China team, Due: Next quarter)
4. 提交支持人员配置计划 (Assigned to: Japan team, Due: In two weeks)
5. 提交 AI 原型的性能基准 (Assigned to: Japan team, Due: In two weeks)

--- Japanese ---
TITLE: 第2四半期グローバル戦略エグゼクティブ会議
SUMMARY: 第2四半期グローバル戦略エグゼクティブ会議では、収益と顧客満足度における成功が取り上げられた一方、運用上の課題、特にアジア地域における倉庫保管の遅延、ソフトウェア統合の問題、および出荷の遅延が特定されました。各チームはこれらの問題に対処し、2週間後のチーム横断的なレビューに備えるためのアクションアイテムが割り当てられました。

KEY POINTS:
1. 中国東部では、サプライヤーのソフトウェアの互換性の問題により、倉庫保管の遅延が発生しています。
2. 東南アジアにおけるマーケティング展開は、翻訳品質の低さにより遅延しており、ローカリゼーションの改善が必要です。
3. 日本市場では、新製品ラインに対する肯定的なフィードバックが見られますが、出荷の遅延に直面しています。
4. AIパーソナライゼーションのプロトタイプは完成しましたが、役員会でのデモを行う前に安定性を向上させる必要があります。
5. 中国チームは、2つの主要なeコマースプラットフォームとの提携交渉を行っており、深センに新しい流通センターを設立することを検討しています。

ACTION ITEMS:
1. 地域横断的な物流改善のためのロードマップを作成する (Assigned to: US team, Due: In two weeks)
2. 統合に必要なリソースの概要を説明する (Assigned to: China team, Due: In two weeks)
3. eコマースパートナーシップを最終決定する (Assigned to: China team, Due: Next quarter)
4. サポート要員計画を提出する (Assigned to: Japan team, Due: In two weeks)
5. AIプロトタイプのパフォーマンスベンチマークを提出する (Assigned to: Japan team, Due: In two weeks)

Results also saved to 'meeting_output_with_translations.json'
```
