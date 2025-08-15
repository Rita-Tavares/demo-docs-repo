---
title: "feat(ui): SwiftUI Pro Mode view with toggle + CTA"
description: "Auto-generated from PR #15"
---

**PR:** [#15](https://github.com/Rita-Tavares/Demo-HelloWorld/pull/15)

### Summary
## What changed?
- Replaced `ContentView` with a SwiftUI layout using NavigationView.
- Added **Pro Mode** toggle with live ON/OFF label.
- Added **CTA button** that updates the welcome message on tap.
- Styled header (bold, blue) and added spacing for readability.

## Why?
- Demo for auto-docs: bigger, realistic UI change so the generated doc clearly shows both summary + code diff.
- Ensures docs are created and updated automatically with each PR merge.

## Impact
- User-facing UI change (safe). No API or data model changes.

## Risks & Rollback
- Low risk; pure UI. Roll back by reverting this PR.

## Docs impact
- [x] Auto-generate page in GitBook (via workflow)
- Section: `changes/`


### Code changes (unified diff)
```diff
diff --git a/Sources/ContentView.swift b/Sources/ContentView.swift
index e6fc636..b9bc84a 100644
--- a/Sources/ContentView.swift
+++ b/Sources/ContentView.swift
@@ -1,19 +1,43 @@
-// Demo: Pro Mode toggle and counter
-@State private var counter = 0
-@State private var proMode = false
+import SwiftUI
 
-VStack(spacing: 16) {
-    Text("🚀 HelloWorld — Pro Mode demo")
-        .font(.largeTitle)
-        .multilineTextAlignment(.center)
+struct ContentView: View {
+    @State private var isProModeEnabled = false
+    @State private var welcomeMessage = "Welcome to the Demo App!"
 
-    Toggle("Enable Pro Mode", isOn: $proMode)
-        .padding()
+    var body: some View {
+        NavigationView {
+            VStack(spacing: 20) {
+                Text(welcomeMessage)
+                    .font(.title)
+                    .fontWeight(.bold)
+                    .foregroundColor(.blue)
+                    .padding()
 
-    HStack(spacing: 12) {
-        Button("-") { counter = max(0, counter - 1) }.buttonStyle(.bordered)
-        Text("\(counter)").font(.title2).monospacedDigit().frame(minWidth: 44)
-        Button("+") { counter += 1 }.buttonStyle(.borderedProminent)
+                Toggle(isOn: $isProModeEnabled) {
+                    Text(isProModeEnabled ? "Pro Mode: ON" : "Pro Mode: OFF")
+                        .font(.headline)
+                }
+                .padding()
+
+                Button(action: {
+                    welcomeMessage = "Thanks for trying the updated version! 🎉"
+                }) {
+                    Text("Tap to Change Message")
+                        .font(.system(size: 18, weight: .medium))
+                        .padding()
+                        .background(Color.green)
+                        .foregroundColor(.white)
+                        .cornerRadius(8)
+                }
+
+                Spacer()
+            }
+            .padding()
+            .navigationTitle("Demo App")
+        }
     }
 }
-.padding()
+
+#Preview {
+    ContentView()
+}
```
