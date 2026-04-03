# CopyQ: Jump Back to Original History Item

A practical CopyQ custom command that lets you jump from a filtered/search result back to the item's original position in clipboard history.

## Why this exists

When using search in CopyQ, the list only shows matched items.  
This is useful for finding content quickly, but sometimes you also want to:

- return to the original history list
- locate the selected item in its real position
- inspect nearby items as context

This command solves that problem.

## What it does

After selecting an item in search results, the command will:

1. return to the original tab
2. clear the active filter
3. locate the selected item in the full history
4. select that item so you can continue browsing its context

## Matching strategy

To improve reliability, the command uses a two-step matching strategy:

1. **Exact item match**  
   Compare the full packed item data, not just plain text.

2. **Text fallback match**  
   If exact matching fails, fall back to text content matching.

In both cases, it searches from the most recent item backward, which helps reduce misalignment when duplicates exist.

## Features

- No extra context tab
- No duplicated history items
- No UUID injection
- No CopyQ source code modification
- Better than plain text-only matching
- Practical for day-to-day clipboard history navigation

## Limitations

This command does **not** assign unique IDs to history entries.

That means:

- if two or more items are completely identical
- and all their data is the same

then CopyQ script-level matching cannot always tell them apart.

In such cases, the command will prefer the most recent matching item.

## Installation

1. Open CopyQ
2. Go to **Commands**
3. Create a new command
4. Paste the contents of [`jump-to-original-history.ini`](https://github.com/yzgolden86/copyq-context-location/blob/main/jump-to-original-history.ini)
5. Save the command

Suggested shortcut:
  Ctrl+Shift+G

## Usage
1. Search in CopyQ history
2. Select a matched item
3. Trigger the command
4. CopyQ will jump back to the original history and select the corresponding item
##  Command file
See:
 commands/jump-to-original-history.ini
## Documentation
For more details, see:
 docs/usage.md
