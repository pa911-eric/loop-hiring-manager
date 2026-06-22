# Contributing

Thanks for helping improve Loop Hiring Manager.

## Good contributions

Changes should make the framework:

- more selective rather than more prolific;
- easier for agents to execute consistently;
- easier for humans to review and override;
- better grounded in current project evidence;
- clearer about checks, budgets, permissions, and terminal states;
- better at recognizing when a loop is unnecessary.

## Before opening a change

Please verify that:

1. the parent still checks existing loops before designing a new one;
2. the pipeline remains capped at three candidates and one trial;
3. no prompt grants itself consequential authority;
4. every new field affects an actual decision;
5. the empty-pipeline outcome remains valid;
6. examples do not imply generic repository requirements.

Keep proposals small and explain the failure mode or ambiguity they address.
