# Multilingual Meeting GenAI Agent

A multilingual meeting assistant that uses generative AI to automatically extract key information, action items, and provide translations from meeting transcripts.

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

## Contributors
Yang Jiang (Momiji) | [Linkedin](https://www.linkedin.com/in/yang-jiang-koyo)

## License
MIT

## Example Output
```
==================================================
MEETING TITLE: Q2 Product Launch Planning Meeting
==================================================

SUMMARY:
The team discussed progress on the Q2 product launch, including backend integration, UI mockups, and analytics platform selection. Action items were assigned for landing page content in English, Chinese, and Japanese, as well as testing Firebase and Mixpanel.

KEY POINTS:
1. Backend integration is complete and ready for final QA
2. Design team will submit final UI mockups by next week
3. Firebase and Mixpanel will be tested in staging by Thursday to determine which analytics platform to use
4. Landing page content updates needed in English, Chinese, and Japanese
5. Final review meeting scheduled for next Monday at 10 AM Pacific

ACTION ITEMS:
1. Coordinate with marketing for English landing page content (Assigned to: John, Due: None)
2. Handle Chinese version of landing page content (Assigned to: Li Wei, Due: None)
3. Handle Japanese translation of landing page content (Assigned to: Yuki, Due: None)
4. Test Firebase and Mixpanel on staging (Assigned to: Team, Due: Thursday)
5. Finalize UI mockups (Assigned to: Design team, Due: Next week)

==================================================
TRANSLATIONS
==================================================

--- Chinese ---
TITLE: 第二季度产品发布计划会议
SUMMARY: 团队讨论了第二季度产品发布的进展，包括后端集成、UI模型以及分析平台选择。指定了英语、中文和日语着陆页内容的行动项，以及测试 Firebase 和 Mixpanel。

KEY POINTS:
1. 后端集成已完成，准备进行最终质量保证 (QA)
2. 设计团队将于下周提交最终 UI 模型
3. 将于周四在预发布环境 (staging) 中测试 Firebase 和 Mixpanel，以确定使用哪个分析平台
4. 需要更新英语、中文和日语的着陆页内容
5. 最终审查会议定于下周一太平洋时间上午 10 点

ACTION ITEMS:
1. 与市场部协调英语着陆页内容 (Assigned to: John, Due: None)
2. 处理中文版着陆页内容 (Assigned to: Li Wei, Due: None)
3. 处理日语着陆页内容的翻译 (Assigned to: Yuki, Due: None)
4. 在预发布环境 (staging) 中测试 Firebase 和 Mixpanel (Assigned to: Team, Due: Thursday)
5. 最终确定 UI 模型 (Assigned to: Design team, Due: Next week)

--- Japanese ---
TITLE: 第2四半期プロダクトローンチ計画会議
SUMMARY: チームは、第2四半期のプロダクトローンチの進捗状況について議論しました。議論内容には、バックエンドの統合、UIモックアップ、および分析プラットフォームの選定が含まれます。英語、中国語、日本語のランディングページコンテンツ、およびFirebaseとMixpanelのテストに関するアクションアイテムが割り当てられました。

KEY POINTS:
1. バックエンドの統合が完了し、最終QAの準備が整いました
2. デザインチームは来週までに最終UIモックアップを提出します
3. FirebaseとMixpanelは、使用する分析プラットフォームを決定するために、木曜日までにステージング環境でテストされます
4. 英語、中国語、日本語のランディングページコンテンツの更新が必要です
5. 最終レビュー会議は、太平洋時間の来週月曜日午前10時に予定されています

ACTION ITEMS:
1. 英語のランディングページコンテンツについてマーケティング部門と連携 (Assigned to: John, Due: None)
2. ランディングページコンテンツの中国語版を担当 (Assigned to: Li Wei, Due: None)
3. ランディングページコンテンツの日本語翻訳を担当 (Assigned to: Yuki, Due: None)
4. ステージング環境でFirebaseとMixpanelをテスト (Assigned to: Team, Due: Thursday)
5. UIモックアップを最終決定 (Assigned to: Design team, Due: Next week)

Results also saved to 'meeting_output_with_translations.json'
```
