# SynomosAI 治理工程工具包 · v0.1-gov-tooling

> 人与 AI 治理工具集（MCP Server + OpenAPI 治理 API）——发布就绪打包版。

- 署名：Logos 诺声@SynomosAI
- 版权：SynomosAI
- 版本：v0.1-gov-tooling
- 许可：MIT

## 包含内容

| 文件 | 说明 |
|---|---|
| nomos_mcp_server.py | MCP Server（stdio），5 个治理工具 |
| nomos_api.py | FastAPI 治理 API（最小版），6 个端点 |
| openapi.yaml | OpenAPI 3.1 规范 |

## MCP 工具（5）

| 工具 | 说明 |
|---|---|
| audit_evidence_chain | 生成 ISO/IEC 42001 + NIST AI RMF 可审计证据工件模板（六类：决策日志/风险登记册/模型卡/变更记录/人类监督证明/事件处置台账） |
| a3_assess | A³ 法则四维评分卡评估（意图/影响/可逆性/监督），返回总分与放行建议 |
| passport_lookup | 查询技能/智能体身份码与溯源（本地台账） |
| compliance_checklist | EU AI Act Art 52a / GB/Z 185 合规清单（面向自主 agent 注册就绪） |
| gov_scan | 对文本做治理/PII/版权/指纹扫描（命中即告警） |

## API 端点（6）

| 方法 | 端点 | 说明 |
|---|---|---|
| GET | /v1/health | 健康检查 |
| POST | /v1/audit/evidence-chain | 生成六类证据工件模板 |
| POST | /v1/a3/assess | A³ 四维评分卡评估 |
| GET | /v1/passport/{skill_id} | 查询智能体身份码/溯源 |
| GET | /v1/compliance/checklist | 合规清单（EU AI Act 52a / GB/Z 185） |
| POST | /v1/gov/scan | 治理/PII/版权/指纹扫描 |

## 本地运行

MCP Server：

    python nomos_mcp_server.py

API（FastAPI）：

    uvicorn nomos_api:app --reload --port 8000

## 版权与许可

© 2026 SynomosAI · MIT License
署名：Logos 诺声@SynomosAI
