---
title: "Update ContentView.swift"
description: "Auto-generated from PR #13"
---

**PR:** [#13](https://github.com/Rita-Tavares/Demo-HelloWorld/pull/13)

### Summary
feat(ui): Add Pro Mode toggle

## What changed?
- Added a counter and toggle for Pro Mode.
- Updated header text.

## Why?
Demonstration for auto-docs system.

## What changed?

## Why?

## How?

## Risks & rollback

## Tests & verification

## UI
<!-- Add screenshots/videos -->

## Docs impact
- [ ] No docs needed
- [x] New page needed
- Suggested title/slug:


### Code changes (unified diff)
```diff
diff --git a/Sources/ContentView.swift b/Sources/ContentView.swift
index 89e9228..4404370 100644
--- a/Sources/ContentView.swift
+++ b/Sources/ContentView.swift
@@ -6,7 +6,7 @@ struct ContentView: View {
 
     var body: some View {
         VStack(spacing: 16) {
-            Text("Welcome to HelloWorld App!!!!!")
+            Text("Welcome to HelloWorld App!")
                 .font(.largeTitle)
                 .multilineTextAlignment(.center)
 
```
