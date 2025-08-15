---
title: "Update ContentView.swift"
description: "Auto-generated from PR #14"
---

**PR:** [#14](https://github.com/Rita-Tavares/Demo-HelloWorld/pull/14)

### Summary
## What changed?
- Added counter and toggle for Pro Mode.
- Updated header text.

## Why?
Demonstration for auto-docs system.

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
index 4404370..e6fc636 100644
--- a/Sources/ContentView.swift
+++ b/Sources/ContentView.swift
@@ -1,62 +1,19 @@
-import SwiftUI
+// Demo: Pro Mode toggle and counter
+@State private var counter = 0
+@State private var proMode = false
 
-struct ContentView: View {
-    @State private var counter = 0
-    @State private var isOn = false
+VStack(spacing: 16) {
+    Text("🚀 HelloWorld — Pro Mode demo")
+        .font(.largeTitle)
+        .multilineTextAlignment(.center)
 
-    var body: some View {
-        VStack(spacing: 16) {
-            Text("Welcome to HelloWorld App!")
-                .font(.largeTitle)
-                .multilineTextAlignment(.center)
-
-            // Counter section
-            HStack(spacing: 12) {
-                Button("-") { counter = max(0, counter - 1) }
-                    .buttonStyle(.bordered)
-                Text("\(counter)")
-                    .font(.title2)
-                    .monospacedDigit()
-                    .frame(minWidth: 44)
-                Button("+") { counter += 1 }
-                    .buttonStyle(.borderedProminent)
-            }
-
-            // Toggle section
-            Toggle(isOn: $isOn) {
-                Text("Enable Pro Mode")
-            }
-            .padding(.horizontal)
-
-            if isOn {
-                ProModeCard(counter: counter)
-                    .transition(.opacity)
-            }
-        }
+    Toggle("Enable Pro Mode", isOn: $proMode)
         .padding()
-        .animation(.default, value: isOn)
-    }
-}
 
-struct ProModeCard: View {
-    let counter: Int
-
-    var body: some View {
-        VStack(spacing: 8) {
-            Text("Pro Mode")
-                .font(.headline)
-            Text("Current counter: \(counter)")
-                .font(.subheadline)
-        }
-        .padding()
-        .frame(maxWidth: .infinity)
-        .background(Color(.secondarySystemBackground))
-        .clipShape(RoundedRectangle(cornerRadius: 12))
-        .shadow(radius: 1)
-        .padding(.horizontal)
+    HStack(spacing: 12) {
+        Button("-") { counter = max(0, counter - 1) }.buttonStyle(.bordered)
+        Text("\(counter)").font(.title2).monospacedDigit().frame(minWidth: 44)
+        Button("+") { counter += 1 }.buttonStyle(.borderedProminent)
     }
 }
-
-#Preview {
-    ContentView()
-}
+.padding()
```
