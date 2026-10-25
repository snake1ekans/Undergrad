---
id: tasknotes
name: TaskNotes
source: vault-native
plugin-type: community
status: enabled
class: FULL
description: "Note-based task management with calendar, pomodoro and time-tracking integration."
has-settings: true
commands:
  - id: "tasknotes:open-calendar-view"
    name: "TaskNotes: Open mini calendar view"
  - id: "tasknotes:open-advanced-calendar-view"
    name: "TaskNotes: Open calendar view"
  - id: "tasknotes:open-tasks-view"
    name: "TaskNotes: Open tasks view"
  - id: "tasknotes:open-agenda-view"
    name: "TaskNotes: Open agenda view"
  - id: "tasknotes:open-pomodoro-view"
    name: "TaskNotes: Open Pomodoro timer"
  - id: "tasknotes:open-kanban-view"
    name: "TaskNotes: Open Kanban board"
  - id: "tasknotes:update-default-base-files"
    name: "TaskNotes: Update default base files"
  - id: "tasknotes:open-pomodoro-stats"
    name: "TaskNotes: Open Pomodoro statistics"
  - id: "tasknotes:open-statistics"
    name: "TaskNotes: Open task & project statistics"
  - id: "tasknotes:create-new-task"
    name: "TaskNotes: Create new task"
  - id: "tasknotes:convert-current-note-to-task"
    name: "TaskNotes: Convert current note to task"
  - id: "tasknotes:convert-to-tasknote"
    name: "TaskNotes: Convert checkbox task to TaskNote"
  - id: "tasknotes:batch-convert-all-tasks"
    name: "TaskNotes: Convert all tasks in note"
  - id: "tasknotes:insert-tasknote-link"
    name: "TaskNotes: Insert tasknote link"
  - id: "tasknotes:create-inline-task"
    name: "TaskNotes: Create new inline task"
  - id: "tasknotes:quick-actions-current-task"
    name: "TaskNotes: Quick actions for current task"
  - id: "tasknotes:quick-actions-task-under-cursor"
    name: "TaskNotes: Quick actions for task under cursor"
  - id: "tasknotes:edit-current-task"
    name: "TaskNotes: Edit current task"
  - id: "tasknotes:cycle-current-task-status"
    name: "TaskNotes: Cycle current task status"
  - id: "tasknotes:cycle-current-task-priority"
    name: "TaskNotes: Cycle current task priority"
  - id: "tasknotes:add-project-to-current-task"
    name: "TaskNotes: Add project to current task"
  - id: "tasknotes:add-subtask-to-current-note"
    name: "TaskNotes: Add subtask to current note"
  - id: "tasknotes:go-to-today"
    name: "TaskNotes: Go to today's note"
  - id: "tasknotes:start-pomodoro"
    name: "TaskNotes: Start Pomodoro timer"
  - id: "tasknotes:stop-pomodoro"
    name: "TaskNotes: Stop Pomodoro timer"
  - id: "tasknotes:pause-pomodoro"
    name: "TaskNotes: Pause/resume Pomodoro timer"
  - id: "tasknotes:refresh-cache"
    name: "TaskNotes: Refresh cache"
  - id: "tasknotes:export-all-tasks-ics"
    name: "TaskNotes: Export all tasks as ICS file"
  - id: "tasknotes:sync-all-tasks-google-calendar"
    name: "TaskNotes: Sync all tasks to Google Calendar"
  - id: "tasknotes:sync-current-task-google-calendar"
    name: "TaskNotes: Sync current task to Google Calendar"
  - id: "tasknotes:view-release-notes"
    name: "TaskNotes: View release notes"
  - id: "tasknotes:start-time-tracking-current-task"
    name: "TaskNotes: Start time tracking for current task"
  - id: "tasknotes:stop-time-tracking-current-task"
    name: "TaskNotes: Stop time tracking for current task"
  - id: "tasknotes:stop-active-time-tracking"
    name: "TaskNotes: Stop active time tracking"
  - id: "tasknotes:start-time-tracking-with-selector"
    name: "TaskNotes: Start time tracking (select task)"
  - id: "tasknotes:edit-time-entries"
    name: "TaskNotes: Edit time entries (select task)"
  - id: "tasknotes:create-or-open-task"
    name: "TaskNotes: Create or open task"
  - id: "tasknotes:create-or-open-task-with-time-tracking"
    name: "TaskNotes: Create or open task and start time tracking"
  - id: "tasknotes:rollover-overdue-scheduled-tasks"
    name: "TaskNotes: Postpone overdue scheduled tasks to today"
---

# TaskNotes

**Description:** Note-based task management with calendar, pomodoro and time-tracking integration.
**Status:** Enabled
**Plugin ID:** tasknotes

## Available Commands

Available command IDs (use execute_command for Obsidian-native commands):
- `tasknotes:open-calendar-view` -- TaskNotes: Open mini calendar view
- `tasknotes:open-advanced-calendar-view` -- TaskNotes: Open calendar view
- `tasknotes:open-tasks-view` -- TaskNotes: Open tasks view
- `tasknotes:open-agenda-view` -- TaskNotes: Open agenda view
- `tasknotes:open-pomodoro-view` -- TaskNotes: Open Pomodoro timer
- `tasknotes:open-kanban-view` -- TaskNotes: Open Kanban board
- `tasknotes:update-default-base-files` -- TaskNotes: Update default base files
- `tasknotes:open-pomodoro-stats` -- TaskNotes: Open Pomodoro statistics
- `tasknotes:open-statistics` -- TaskNotes: Open task & project statistics
- `tasknotes:create-new-task` -- TaskNotes: Create new task
- `tasknotes:convert-current-note-to-task` -- TaskNotes: Convert current note to task
- `tasknotes:convert-to-tasknote` -- TaskNotes: Convert checkbox task to TaskNote
- `tasknotes:batch-convert-all-tasks` -- TaskNotes: Convert all tasks in note
- `tasknotes:insert-tasknote-link` -- TaskNotes: Insert tasknote link
- `tasknotes:create-inline-task` -- TaskNotes: Create new inline task
- `tasknotes:quick-actions-current-task` -- TaskNotes: Quick actions for current task
- `tasknotes:quick-actions-task-under-cursor` -- TaskNotes: Quick actions for task under cursor
- `tasknotes:edit-current-task` -- TaskNotes: Edit current task
- `tasknotes:cycle-current-task-status` -- TaskNotes: Cycle current task status
- `tasknotes:cycle-current-task-priority` -- TaskNotes: Cycle current task priority
- `tasknotes:add-project-to-current-task` -- TaskNotes: Add project to current task
- `tasknotes:add-subtask-to-current-note` -- TaskNotes: Add subtask to current note
- `tasknotes:go-to-today` -- TaskNotes: Go to today's note
- `tasknotes:start-pomodoro` -- TaskNotes: Start Pomodoro timer
- `tasknotes:stop-pomodoro` -- TaskNotes: Stop Pomodoro timer
- `tasknotes:pause-pomodoro` -- TaskNotes: Pause/resume Pomodoro timer
- `tasknotes:refresh-cache` -- TaskNotes: Refresh cache
- `tasknotes:export-all-tasks-ics` -- TaskNotes: Export all tasks as ICS file
- `tasknotes:sync-all-tasks-google-calendar` -- TaskNotes: Sync all tasks to Google Calendar
- `tasknotes:sync-current-task-google-calendar` -- TaskNotes: Sync current task to Google Calendar
- `tasknotes:view-release-notes` -- TaskNotes: View release notes
- `tasknotes:start-time-tracking-current-task` -- TaskNotes: Start time tracking for current task
- `tasknotes:stop-time-tracking-current-task` -- TaskNotes: Stop time tracking for current task
- `tasknotes:stop-active-time-tracking` -- TaskNotes: Stop active time tracking
- `tasknotes:start-time-tracking-with-selector` -- TaskNotes: Start time tracking (select task)
- `tasknotes:edit-time-entries` -- TaskNotes: Edit time entries (select task)
- `tasknotes:create-or-open-task` -- TaskNotes: Create or open task
- `tasknotes:create-or-open-task-with-time-tracking` -- TaskNotes: Create or open task and start time tracking
- `tasknotes:rollover-overdue-scheduled-tasks` -- TaskNotes: Postpone overdue scheduled tasks to today

## Plugin API

This plugin exposes a JavaScript API. Use call_plugin_api to call these methods:
- `hasCapability` -- call via call_plugin_api("tasknotes", "hasCapability", [args])
- `parseNaturalLanguage` -- call via call_plugin_api("tasknotes", "parseNaturalLanguage", [args])
- `getModelConfig` -- call via call_plugin_api("tasknotes", "getModelConfig", [args])
- `validateTask` -- call via call_plugin_api("tasknotes", "validateTask", [args])
- `validateTaskPatch` -- call via call_plugin_api("tasknotes", "validateTaskPatch", [args])
- `normalizeError` -- call via call_plugin_api("tasknotes", "normalizeError", [args])
- `updateDefaultBasesFiles` -- call via call_plugin_api("tasknotes", "updateDefaultBasesFiles", [args])
- `getStatuses` -- call via call_plugin_api("tasknotes", "getStatuses", [args])
- `getPriorities` -- call via call_plugin_api("tasknotes", "getPriorities", [args])
- `getUserFields` -- call via call_plugin_api("tasknotes", "getUserFields", [args])
- `getFieldDefinitions` -- call via call_plugin_api("tasknotes", "getFieldDefinitions", [args])
- `getFilterPropertyDefinitions` -- call via call_plugin_api("tasknotes", "getFilterPropertyDefinitions", [args])
- `queryTasks` -- call via call_plugin_api("tasknotes", "queryTasks", [args])
- `validateRuntimeQuery` -- call via call_plugin_api("tasknotes", "validateRuntimeQuery", [args])
- `normalizeRuntimeQueryOrThrow` -- call via call_plugin_api("tasknotes", "normalizeRuntimeQueryOrThrow", [args])
- `explainRuntimeQuery` -- call via call_plugin_api("tasknotes", "explainRuntimeQuery", [args])
- `getFilterOptions` -- call via call_plugin_api("tasknotes", "getFilterOptions", [args])
- `normalizeRuntimeQueryForExecution` -- call via call_plugin_api("tasknotes", "normalizeRuntimeQueryForExecution", [args])
- `normalizeRuntimeTaskQuery` -- call via call_plugin_api("tasknotes", "normalizeRuntimeTaskQuery", [args])
- `normalizeRuntimePredicate` -- call via call_plugin_api("tasknotes", "normalizeRuntimePredicate", [args])
- `normalizeRuntimeCondition` -- call via call_plugin_api("tasknotes", "normalizeRuntimeCondition", [args])
- `normalizeRuntimeSorts` -- call via call_plugin_api("tasknotes", "normalizeRuntimeSorts", [args])
- `normalizeRuntimeGroups` -- call via call_plugin_api("tasknotes", "normalizeRuntimeGroups", [args])
- `runtimeQueryToFilterQuery` -- call via call_plugin_api("tasknotes", "runtimeQueryToFilterQuery", [args])
- `runtimePredicateToFilterNode` -- call via call_plugin_api("tasknotes", "runtimePredicateToFilterNode", [args])
- `runtimeConditionToFilterNode` -- call via call_plugin_api("tasknotes", "runtimeConditionToFilterNode", [args])
- `resolveRuntimeQueryField` -- call via call_plugin_api("tasknotes", "resolveRuntimeQueryField", [args])
- `resolveRuntimeUserField` -- call via call_plugin_api("tasknotes", "resolveRuntimeUserField", [args])
- `runtimeFieldToSortKey` -- call via call_plugin_api("tasknotes", "runtimeFieldToSortKey", [args])
- `runtimeFieldToGroupKey` -- call via call_plugin_api("tasknotes", "runtimeFieldToGroupKey", [args])
- `getTaskStats` -- call via call_plugin_api("tasknotes", "getTaskStats", [args])
- `getTimeSummary` -- call via call_plugin_api("tasknotes", "getTimeSummary", [args])
- `getTaskTimeData` -- call via call_plugin_api("tasknotes", "getTaskTimeData", [args])
- `getHealth` -- call via call_plugin_api("tasknotes", "getHealth", [args])
- `showTaskMenu` -- call via call_plugin_api("tasknotes", "showTaskMenu", [args])
- `showTaskMenuAtElement` -- call via call_plugin_api("tasknotes", "showTaskMenuAtElement", [args])
- `populateTaskMenu` -- call via call_plugin_api("tasknotes", "populateTaskMenu", [args])
- `buildTaskContextMenu` -- call via call_plugin_api("tasknotes", "buildTaskContextMenu", [args])
- `defaultTaskMenuUpdateHandler` -- call via call_plugin_api("tasknotes", "defaultTaskMenuUpdateHandler", [args])
- `getVaultInfo` -- call via call_plugin_api("tasknotes", "getVaultInfo", [args])
- `computeTaskStats` -- call via call_plugin_api("tasknotes", "computeTaskStats", [args])
- `getTask` -- call via call_plugin_api("tasknotes", "getTask", [args])
- `listTasks` -- call via call_plugin_api("tasknotes", "listTasks", [args])
- `getParentTasks` -- call via call_plugin_api("tasknotes", "getParentTasks", [args])
- `getSubtasks` -- call via call_plugin_api("tasknotes", "getSubtasks", [args])
- `getTaskDependencies` -- call via call_plugin_api("tasknotes", "getTaskDependencies", [args])
- `getBlockingTasks` -- call via call_plugin_api("tasknotes", "getBlockingTasks", [args])
- `getTaskRelationships` -- call via call_plugin_api("tasknotes", "getTaskRelationships", [args])
- `createTask` -- call via call_plugin_api("tasknotes", "createTask", [args])
- `updateTask` -- call via call_plugin_api("tasknotes", "updateTask", [args])
- `completeTask` -- call via call_plugin_api("tasknotes", "completeTask", [args])
- `rescheduleTask` -- call via call_plugin_api("tasknotes", "rescheduleTask", [args])
- `archiveTask` -- call via call_plugin_api("tasknotes", "archiveTask", [args])
- `moveTask` -- call via call_plugin_api("tasknotes", "moveTask", [args])
- `deleteTask` -- call via call_plugin_api("tasknotes", "deleteTask", [args])
- `uncompleteTask` -- call via call_plugin_api("tasknotes", "uncompleteTask", [args])
- `startTimeEntry` -- call via call_plugin_api("tasknotes", "startTimeEntry", [args])
- `stopTimeEntry` -- call via call_plugin_api("tasknotes", "stopTimeEntry", [args])
- `setTaskProperty` -- call via call_plugin_api("tasknotes", "setTaskProperty", [args])
- `updateStringList` -- call via call_plugin_api("tasknotes", "updateStringList", [args])
- `addReminder` -- call via call_plugin_api("tasknotes", "addReminder", [args])
- `removeReminder` -- call via call_plugin_api("tasknotes", "removeReminder", [args])
- `addDependency` -- call via call_plugin_api("tasknotes", "addDependency", [args])
- `removeDependency` -- call via call_plugin_api("tasknotes", "removeDependency", [args])
- `startTime` -- call via call_plugin_api("tasknotes", "startTime", [args])
- `stopTime` -- call via call_plugin_api("tasknotes", "stopTime", [args])
- `appendTimeEntry` -- call via call_plugin_api("tasknotes", "appendTimeEntry", [args])
- `deleteTimeEntry` -- call via call_plugin_api("tasknotes", "deleteTimeEntry", [args])
- `getActiveTimeEntries` -- call via call_plugin_api("tasknotes", "getActiveTimeEntries", [args])
- `getSettingsSnapshot` -- call via call_plugin_api("tasknotes", "getSettingsSnapshot", [args])
- `registerExtension` -- call via call_plugin_api("tasknotes", "registerExtension", [args])
- `getExtension` -- call via call_plugin_api("tasknotes", "getExtension", [args])
- `requireExtension` -- call via call_plugin_api("tasknotes", "requireExtension", [args])
- `hasExtension` -- call via call_plugin_api("tasknotes", "hasExtension", [args])
- `listExtensions` -- call via call_plugin_api("tasknotes", "listExtensions", [args])
- `extensionInfo` -- call via call_plugin_api("tasknotes", "extensionInfo", [args])
- `getExtensionCapabilities` -- call via call_plugin_api("tasknotes", "getExtensionCapabilities", [args])
- `normalizeExtensionNamespace` -- call via call_plugin_api("tasknotes", "normalizeExtensionNamespace", [args])
- `normalizeExtensionCapability` -- call via call_plugin_api("tasknotes", "normalizeExtensionCapability", [args])
- `startPomodoro` -- call via call_plugin_api("tasknotes", "startPomodoro", [args])
- `stopPomodoro` -- call via call_plugin_api("tasknotes", "stopPomodoro", [args])
- `pausePomodoro` -- call via call_plugin_api("tasknotes", "pausePomodoro", [args])
- `resumePomodoro` -- call via call_plugin_api("tasknotes", "resumePomodoro", [args])
- `assignPomodoroTask` -- call via call_plugin_api("tasknotes", "assignPomodoroTask", [args])
- `getPomodoroSessions` -- call via call_plugin_api("tasknotes", "getPomodoroSessions", [args])
- `getPomodoroStats` -- call via call_plugin_api("tasknotes", "getPomodoroStats", [args])
- `copyPomodoroState` -- call via call_plugin_api("tasknotes", "copyPomodoroState", [args])
- `toggleRecurringComplete` -- call via call_plugin_api("tasknotes", "toggleRecurringComplete", [args])
- `materializeOccurrence` -- call via call_plugin_api("tasknotes", "materializeOccurrence", [args])
- `toggleRecurringSkipped` -- call via call_plugin_api("tasknotes", "toggleRecurringSkipped", [args])
- `on` -- call via call_plugin_api("tasknotes", "on", [args])
- `onLifecycle` -- call via call_plugin_api("tasknotes", "onLifecycle", [args])
- `emitLifecycle` -- call via call_plugin_api("tasknotes", "emitLifecycle", [args])
- `off` -- call via call_plugin_api("tasknotes", "off", [args])
- `resolveTaskReference` -- call via call_plugin_api("tasknotes", "resolveTaskReference", [args])
- `taskReferenceMatches` -- call via call_plugin_api("tasknotes", "taskReferenceMatches", [args])
- `resolveTaskReferencePath` -- call via call_plugin_api("tasknotes", "resolveTaskReferencePath", [args])
- `requireTask` -- call via call_plugin_api("tasknotes", "requireTask", [args])
- `requireTaskFile` -- call via call_plugin_api("tasknotes", "requireTaskFile", [args])
- `normalizeTaskPath` -- call via call_plugin_api("tasknotes", "normalizeTaskPath", [args])
- `withMutationContext` -- call via call_plugin_api("tasknotes", "withMutationContext", [args])
- `normalizeUpdatedEvent` -- call via call_plugin_api("tasknotes", "normalizeUpdatedEvent", [args])
- `normalizeDeletedEvent` -- call via call_plugin_api("tasknotes", "normalizeDeletedEvent", [args])
- `normalizeLifecycleEvent` -- call via call_plugin_api("tasknotes", "normalizeLifecycleEvent", [args])
- `buildEventPayloadBase` -- call via call_plugin_api("tasknotes", "buildEventPayloadBase", [args])
- `getMutationContext` -- call via call_plugin_api("tasknotes", "getMutationContext", [args])
- `normalizeRawEvent` -- call via call_plugin_api("tasknotes", "normalizeRawEvent", [args])
- `normalizePomodoroEvent` -- call via call_plugin_api("tasknotes", "normalizePomodoroEvent", [args])

Note: Dynamically discovered methods require user approval for each call unless marked as safe in settings.

## Configuration File

Settings path: `.obsidian/plugins/tasknotes/data.json`

To configure this plugin programmatically:
1. Read the config: read_file(".obsidian/plugins/tasknotes/data.json")
2. Understand the settings structure and modify values as needed
3. Write changes: write_file(".obsidian/plugins/tasknotes/data.json", updatedJSON)

Do NOT ask the user to open Settings UI. Modify data.json directly.

## Current Configuration

These are the plugin's current settings (sensitive values redacted):

```
tasksFolder: _functional/TaskNotes/Tasks
moveArchivedTasks: false
archiveFolder: TaskNotes/Archive
taskTag: task
taskIdentificationMethod: tag
hideIdentifyingTagsInCards: false
hideIdentifyingTagsMode: all
defaultTaskPriority: normal
defaultTaskStatus: open
taskOrgFiltersCollapsed: false
taskFilenameFormat: zettel
storeTitleInFilename: true
customFilenameTemplate: {{title}}
occurrenceFilenameTemplateProperty: occurrenceFilenameTemplate
taskCreationDefaults:
  useParentNoteForTaskCreation: false
  useParentNoteAsProject: false
  useParentHeaderAsProject: false
  inheritParentTaskProperties: false
  defaultTimeEstimate: 0
  defaultRecurrence: none
  defaultDueDate: none
  defaultDueTime: none
  defaultScheduledDate: today
  defaultScheduledTime: none
  useBodyTemplate: false
  useOccurrenceBodyTemplate: false
openTaskAfterCreation: none
calendarViewSettings:
  defaultView: dayGridMonth
  customDayCount: 3
  slotDuration: 00:30:00
  slotMinTime: 08:00:00
  slotMaxTime: 24:00:00
  scrollTime: 08:00:00
  firstDay: 1
  timeFormat: 24
  showWeekends: true
  defaultShowScheduled: true
  defaultShowDue: true
  defaultShowDueWhenScheduled: true
  defaultShowScheduledToDueSpan: false
  defaultShowTimeEntries: false
  defaultShowRecurring: true
  defaultShowICSEvents: true
  enableTimeblocking: false
  defaultShowTimeblocks: true
  defaultTimeblockColor: #6366f1
  timeblockAttachmentSearchOrder: name-asc
  nowIndicator: true
  selectMirror: true
  weekNumbers: false
  showTodayHighlight: true
  eventMinHeight: 15
  slotEventOverlap: true
  dayMaxEvents: true
  dayMaxEventRows: false
pomodoroWorkDuration: 25
pomodoroShortBreakDuration: 5
pomodoroLongBreakDuration: 15
pomodoroLongBreakInterval: 4
pomodoroAutoStartBreaks: true
pomodoroAutoStartWork: false
pomodoroNotifications: true
pomodoroSoundEnabled: true
pomodoroSoundVolume: 50
pomodoroStorageLocation: plugin
pomodoroMobileSidebar: tab
showPomodoroInStatusBar: true
enableTaskLinkOverlay: true
disableOverlayOnAlias: false
enableInstantTaskConvert: true
useDefaultsOnInstantConvert: true
preserveCheckboxOnConvert: false
taskModalTabMovesFocus: true
enableNaturalLanguageInput: true
nlpDefaultToScheduled: true
nlpLanguage: en
uiLanguage: system
statusSuggestionTrigger: *
nlpTriggers:
  triggers: [5 items]
singleClickAction: edit
doubleClickAction: openNote
projectAutosuggest:
  enableFuzzy: false
  rows: [{title|n(Title)}, {aliases|n(Aliases)}, {file.path|n(Path)}]
  showAdvanced: false
inlineTaskConvertFolder: {{currentNotePath}}
disableNoteIndexing: false
suggestionDebounceMs: 0
fieldMapping:
  title: title
  status: status
  priority: priority
  due: due
  scheduled: scheduled
  contexts: contexts
  projects: projects
  attachments: attachments
  timeEstimate: timeEstimate
  completedDate: completedDate
  dateCreated: dateCreated
  dateModified: dateModified
  recurrence: recurrence
  recurrenceAnchor: recurrence_anchor
  recurrenceParent: recurrence_parent
  occurrenceDate: occurrence_date
  occurrenceMaterialization: occurrence_materialization
  occurrenceNextTrigger: occurrence_next_trigger
  occurrenceTemplate: occurrence_template
  occurrencePastHorizon: occurrence_past_horizon
  occurrenceFutureHorizon: occurrence_future_horizon
  archiveTag: archived
  timeEntries: timeEntries
  completeInstances: complete_instances
  skippedInstances: skipped_instances
  blockedBy: blockedBy
  pomodoros: pomodoros
  icsEventId: icsEventId
  icsEventTag: ics_event
  googleCalendarEventId: googleCalendarEventId
  googleCalendarExceptionEventId: googleCalendarExceptionEventId
  googleCalendarExceptionOriginalScheduled: googleCalendarExceptionOriginalScheduled
  googleCalendarMovedOriginalDates: googleCalendarMovedOriginalDates
  reminders: reminders
  sortOrder: tasknotes_manual_order
customStatuses: [4 items: {...}, {...}, {...}...]
customPriorities: [4 items]
recurrenceMigrated: false
showReleaseNotesOnUpdate: true
checkForUpdatesOnStartup: true
starterNoteCreated: true
showTrackedTasksInStatusBar: false
autoStopTimeTrackingOnComplete: true
autoStopTimeTrackingNotification: false
showRelationships: true
relationshipsPosition: bottom
showTaskCardInNote: true
showCompletedTaskStrikethrough: true
completionMenuAsSubmenu: true
showExpandableSubtasks: true
expandSubtasksByDefault: false
subtaskChevronPosition: right
viewsButtonAlignment: right
hideCompletedFromOverdue: true
icsIntegration:
  icsNoteFilenameFormat: title
  customICSNoteFilenameTemplate: {title}
  enableAutoExport: false
  autoExportPath: tasknotes-calendar.ics
  autoExportInterval: 60
  useDurationForExport: false
  excludeArchivedFromExport: false
  excludeCompletedFromExport: false
  requireDueDateForExport: false
  requireScheduledDateForExport: false
  useICSEndAsDue: false
  recurringEventRelatedNotesMode: series
enableNotifications: true
notificationType: system
notificationSoundEnabled: false
notificationSoundVolume: 50
enableAPI: false
apiPort: 8080
enableMCP: false
modalFieldsConfig:
  fields: [9 items: {...}, {...}, {...}...]
  groups: [5 items: {...}, {...}, {...}...]
enableModalSplitLayout: true
defaultVisibleProperties: [status, priority, due, scheduled, projects, contexts, tags, blocked, blocking]
inlineVisibleProperties: [status, priority, due, scheduled, recurrence]
enableBases: true
enableMdbaseSpec: false
autoCreateDefaultBasesFiles: true
commandFileMapping:
  open-calendar-view: _functional/TaskNotes/Views/mini-calendar-default.base
  open-kanban-view: _functional/TaskNotes/Views/kanban-default.base
  open-tasks-view: _functional/TaskNotes/Views/tasks-default.base
  open-advanced-calendar-view: _functional/TaskNotes/Views/calendar-default.base
  open-agenda-view: _functional/TaskNotes/Views/agenda-default.base
  pomodoro-stats-base: _functional/TaskNotes/Views/pomodoro-stats.base
  relationships: _functional/TaskNotes/Views/relationships.base
maintainDueDateOffsetInRecurring: false
resetCheckboxesOnRecurrence: false
useFrontmatterMarkdownLinks: false
enableGoogleCalendar: false
enableMicrosoftCalendar: false
disableCalendarOnMobile: false
googleCalendarExport:
  enabled: false
  syncOnTaskCreate: true
  syncOnTaskUpdate: true
  syncOnTaskComplete: true
  syncOnTaskDelete: true
  eventTitleTemplate: {{title}}
  includeDescription: true
  syncTrigger: scheduled
  createAsAllDay: true
  defaultEventDuration: 60
  includeObsidianLink: true
enableDebugLogging: false
lastSeenVersion: 4.13.8
lastNotifiedReleaseVersion: 4.14.0
pomodoroState:
  isRunning: false
  timeRemaining: 1500
lastPomodoroDate: 2026-10-06
```
(3 sensitive field(s) redacted)

For full settings, read: `.obsidian/plugins/tasknotes/data.json`

## Documentation

For detailed plugin documentation (commands, options, dependencies):
read_file(".vault-operator/plugin-skills/tasknotes.readme.md")

## Usage

When the user asks for functionality related to TaskNotes:
1. Read the plugin documentation (.readme.md) to understand capabilities and dependencies
2. Read the config file (.obsidian/plugins/tasknotes/data.json). If it does not exist, that is normal -- create it with the required settings
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
