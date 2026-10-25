---
id: vault-operator
name: Vault Operator
source: vault-native
plugin-type: community
status: enabled
class: FULL
description: "Agentic AI operating layer for your vault. Discovers and uses installed plugins, maintains persistent unified memory, and adapts to your workflows, skills and tools with full safety controls."
has-settings: true
commands:
  - id: "vault-operator:open-agent-sidebar"
    name: "Vault Operator: Open agent sidebar"
  - id: "vault-operator:new-chat-session"
    name: "Vault Operator: New chat session (parallel)"
  - id: "vault-operator:open-inline-ai-menu"
    name: "Vault Operator: Open inline AI chat"
  - id: "vault-operator:save-conversation-to-memory"
    name: "Vault Operator: Save conversation to memory"
  - id: "vault-operator:generate-memory-soak-report"
    name: "Vault Operator: Generate memory soak report"
  - id: "vault-operator:ba25-run-frontmatter-backfill"
    name: "Vault Operator: Run frontmatter backfill job"
  - id: "vault-operator:ba25-run-inbox-triage"
    name: "Vault Operator: Run inbox triage on the configured auto-trigger property"
  - id: "vault-operator:ba25-refresh-moc-pages"
    name: "Vault Operator: Refresh map-of-content pages now (marker block)"
  - id: "vault-operator:ba25-update-hubs"
    name: "Vault Operator: Update links (rebuild incoming-links tables)"
  - id: "vault-operator:ba25-inject-moc-markers"
    name: "Vault Operator: Inject initial map-of-content markers into cluster candidates"
  - id: "vault-operator:ba25-refresh-top-hub-block"
    name: "Vault Operator: Regenerate top-hub block now"
  - id: "vault-operator:toggle-implicit-connection-banner"
    name: "Vault Operator: Toggle implicit connection banner"
  - id: "vault-operator:open-setup-wizard"
    name: "Vault Operator: Open setup wizard"
---

# Vault Operator

**Description:** Agentic AI operating layer for your vault. Discovers and uses installed plugins, maintains persistent unified memory, and adapts to your workflows, skills and tools with full safety controls.
**Status:** Enabled
**Plugin ID:** vault-operator

## Available Commands

Available command IDs (use execute_command for Obsidian-native commands):
- `vault-operator:open-agent-sidebar` -- Vault Operator: Open agent sidebar
- `vault-operator:new-chat-session` -- Vault Operator: New chat session (parallel)
- `vault-operator:open-inline-ai-menu` -- Vault Operator: Open inline AI chat
- `vault-operator:save-conversation-to-memory` -- Vault Operator: Save conversation to memory
- `vault-operator:generate-memory-soak-report` -- Vault Operator: Generate memory soak report
- `vault-operator:ba25-run-frontmatter-backfill` -- Vault Operator: Run frontmatter backfill job
- `vault-operator:ba25-run-inbox-triage` -- Vault Operator: Run inbox triage on the configured auto-trigger property
- `vault-operator:ba25-refresh-moc-pages` -- Vault Operator: Refresh map-of-content pages now (marker block)
- `vault-operator:ba25-update-hubs` -- Vault Operator: Update links (rebuild incoming-links tables)
- `vault-operator:ba25-inject-moc-markers` -- Vault Operator: Inject initial map-of-content markers into cluster candidates
- `vault-operator:ba25-refresh-top-hub-block` -- Vault Operator: Regenerate top-hub block now
- `vault-operator:toggle-implicit-connection-banner` -- Vault Operator: Toggle implicit connection banner
- `vault-operator:open-setup-wizard` -- Vault Operator: Open setup wizard

## Configuration File

Settings path: `.obsidian/plugins/vault-operator/data.json`

To configure this plugin programmatically:
1. Read the config: read_file(".obsidian/plugins/vault-operator/data.json")
2. Understand the settings structure and modify values as needed
3. Write changes: write_file(".obsidian/plugins/vault-operator/data.json", updatedJSON)

Do NOT ask the user to open Settings UI. Modify data.json directly.

## Current Configuration

These are the plugin's current settings (sensitive values redacted):

```
defaultProvider: anthropic
currentMode: summarizer
customModes: [2 items: {...}, {...}...]
globalCustomInstructions: Use Templates 
autoApproval:
  enabled: true
  noteEdits: true
  vaultChanges: false
  web: false
  mcp: true
  subtasks: false
  skills: false
  pluginApiRead: false
  pluginApiWrite: false
  recipes: false
  sandbox: false
paranoidMode: false
autoApprovalRules:
  readOperations: true
  writeToTempFiles: false
advancedApi:
  consecutiveMistakeLimit: 3
  rateLimitMs: 0
  approvalTimeoutMinutes: 10
  condensingEnabled: true
  condensingThreshold: 50
  powerSteeringFrequency: 0
  maxIterations: 10
  maxSubtaskDepth: 2
  microcompactionEnabled: true
  rollingSummaryThreshold: 50
  costWarnThresholdEur: 0
  telemetryRecordPromptPreview: false
enableSemanticIndex: true
embeddingModels: [1 items]
activeEmbeddingModelKey: bge-large:335m|ollama
semanticBatchSize: 20
semanticAutoIndex: never
semanticIndexPdfs: true
_layoutUpgradePromptShown: true
_pdfReindexHintShown: true
_pdfReindexCompleted: false
semanticChunkSize: 2000
enableContextualRetrieval: true
hydeEnabled: false
weightedFusionEnabled: true
semanticAutoIndexOnChange: false
enableGraphExpansion: true
graphExpansionHops: 1
mocPropertyNames: [moc]
enableImplicitConnections: true
implicitThreshold: 0.7
enableSuggestionBanner: true
categoryProperty: type
backlinksProperty: related
summaryProperty: description
sourceNamingConvention: Author-Year_Title
enableSynthesisButton: true
enableVaultHealthCheck: true
enableReranking: true
rerankCandidates: 20
grantProvenance:
  autoApproval:noteEdits:
    origin: card
    at: 1788977338150
  autoApproval:mcp:
    origin: card
    at: 1789672073896
enableMcpServer: false
mcpAllowWriteTools: false
enableRemoteRelay: false
enableCheckpoints: true
checkpointTimeoutSeconds: 30
checkpointAutoCleanup: true
respectObsidianExcludedFiles: true
webTools:
  enabled: false
  provider: none
enableChatHistory: true
memory:
  enabled: true
  autoExtractSessions: true
  extractionThreshold: 6
  v2MigrationStatus: completed
  crossSurface:
    defaultSyncMode: auto
    perProvider:
      obsilo: global
      claude-ai: global
      claude-code: global
      chatgpt: manual
      perplexity: manual
      unknown: manual
    livingDocumentByDefault: true
    strictSourceIsolation: false
  lastAgingRunAt: 2026-10-25T17:00:11.347Z
  lastCapabilityHash: ae633956
chatLinking:
  enabled: true
autoAddActiveFileContext: false
sendWithEnter: true
lastChatModelByProvider:
  ollama-main: gemma4:12b
  anthropic-main: claude-haiku-4-5-20251001
persistChatModel: true
includeCurrentTimeInContext: false
customPrompts: [3 items: {...}, {...}, {...}...]
vaultDNA:
  enabled: true
  skillToggles:
    random-note: false
    slides: false
    theme: true
    file-explorer: true
skillVersioning:
  retentionCount: 20
backup:
  autoDailyEnabled: false
  autoDailyTargetPath: .vault-operator/cache/backups
  retentionCount: 7
  lastAutoBackupAt: 0
pluginApi:
  enabled: true
  defaultTimeoutMs: 10000
  autoPromotionEnabled: true
  autoPromotionThreshold: 3
recipes:
  enabled: false
mastery:
  enabled: true
  recipeBudget: 2000
  learnedRecipesEnabled: true
onboarding:
  completed: false
  currentStep: backup
  startedAt: 2026-09-09T15:59:30.691Z
  firstRunModalShownCount: 1
  dontShowFirstRunAgain: false
  modalCompleted: true
sandboxMode: auto
safeStoragePlaintextFallbackAcknowledged: false
frontmatterOperatorHintDismissed: false
taskExtraction:
  enabled: true
  taskFolder: Tasks
  preferTaskNotesPlugin: true
  taskNotesHintDismissed: false
kiloLastValidatedAt: 0
chatgptOAuthExpiresAt: 0
chatgptOAuthModel: gpt-5-codex
chatgptOAuthDisclaimerAcknowledgedAt: 0
debugMode: false
agentFolderPath: .vault-operator
defaultOutputFolder: Inbox/
autoTaskRouter:
  enabled: true
leanSystemPrompt: false
vaultIngest:
  summaryPrompt:
    template: [string, 641 chars]
  autoSummary:
    enabled: false
    writeFrontmatter: false
    frontmatterProperty: description
  autoTrigger:
    enabled: false
    propertyName: type
    propertyValue: source
    notification: false
  pdfStrategy: page-refs
  topHubBlock:
    enabled: false
    privacyAcknowledged: false
  incomingLinksBlock:
    enabled: true
    threshold: 10
  stufe2Hint:
    enabled: false
    hintThresholdScore: 70
    minDaysSinceCheck: 30
    perClusterCooldownDays: 7
    maxHintsPerDay: 5
  stufe3PeriodicJob:
    enabled: false
freshness:
  writeFrontmatter: false
  externalSources:
    enabled: false
  allowFrontierEscalation: false
  frontierConfidenceThreshold: 0.7
  frontierSeverityFilter: [contradicts, outdated]
  excludePaths: [Private/, Personal/, Medical/, Clients/]
  weeklyBudgetUsd: 2
  writeReport: true
vaultHealth:
  silenceWithContextOrphans: true
  orphanExcludePathPrefixes: [TaskNotes/]
  reciprocalProperties: [1 items]
providerConfigs: [2 items: {...}, {...}...]
activeProviderId: anthropic-main
defaultMainModelTier: mid
_layoutMigrationStatus: pending
_globalStorageMigrated: true
_forcedWorkflowVaultMigrated: true
_mcpPerModeMigrated: true
_orphanExcludeLegacyCleaned: true
_freshnessVerdictLiteralsMigrated: true
_parentDirMigrated: true
_pluginDataDirsMigrated: true
_legacyVaultDirsCleaned: true
_historyRepairStatus: complete
schemaVersion: 2026.5.15
_encrypted: true
```
(14 sensitive field(s) redacted)

For full settings, read: `.obsidian/plugins/vault-operator/data.json`

## Documentation

For detailed plugin documentation (commands, options, dependencies):
read_file(".vault-operator/plugin-skills/vault-operator.readme.md")

## Usage

When the user asks for functionality related to Vault Operator:
1. Read the plugin documentation (.readme.md) to understand capabilities and dependencies
2. Read the config file (.obsidian/plugins/vault-operator/data.json). If it does not exist, that is normal -- create it with the required settings
3. Configure the plugin by writing data.json with the values needed for the task
4. Execute the task using the appropriate tool:
   - For Obsidian-native commands (including file export): use execute_command
   - For CLI-based conversion needing Pandoc/LaTeX: use execute_recipe
   - For data queries: use call_plugin_api
5. If a command opens a UI dialog, tell the user what to click.

CRITICAL RULES:
- Prefer native Obsidian commands over external tools when both can accomplish the task.
- NEVER create fake output files. If the user asks for a PDF/DOCX/image export, use execute_recipe -- do NOT write content to a .pdf file yourself.
- If a dependency is missing (e.g. Pandoc), tell the user what to install.
IMPORTANT: After reading this file, ALWAYS take action or respond. Never end silently.
