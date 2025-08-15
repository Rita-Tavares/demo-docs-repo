---
title: "Update ContentView.swift"
description: "Auto-generated from PR #16"
---

**PR:** [#16](https://github.com/Rita-Tavares/Demo-HelloWorld/pull/16)

### Summary
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
index b9bc84a..347657c 100644
--- a/Sources/ContentView.swift
+++ b/Sources/ContentView.swift
@@ -2,7 +2,7 @@ import SwiftUI
 
 struct ContentView: View {
     @State private var isProModeEnabled = false
-    @State private var welcomeMessage = "Welcome to the Demo App!"
+    @State private var welcomeMessage = "Welcome to the Demo App"
 
     var body: some View {
         NavigationView {
```
