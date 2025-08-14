---
title: "Update ContentView.swift"
description: "Auto-generated from PR #8"
---

**PR:** [#8](https://github.com/Rita-Tavares/Demo-HelloWorld/pull/8)

### Summary
- This page was generated automatically when the PR merged.

### Swift Code changes (unified diff)

```swift
diff --git a/Sources/ContentView.swift b/Sources/ContentView.swift
index 52484ae..618aeba 100644
--- a/Sources/ContentView.swift
+++ b/Sources/ContentView.swift
@@ -1,12 +1,28 @@
 import SwiftUI
 
 struct ContentView: View {
+    @State private var counter = 0
+
     var body: some View {
-        VStack {
-            Text("Hello, world!")
-                .font(.title)
-                .padding()
+        VStack(spacing: 20) {
+            Text("Welcome to HelloWorld App")
+                .font(.largeTitle)
+                .multilineTextAlignment(.center)
+
+            Text("You've tapped \(counter) times")
+                .font(.headline)
+
+            Button(action: {
+                counter += 1
+            }) {
+                Text("Tap me")
+                    .padding()
+                    .background(Color.blue)
+                    .foregroundColor(.white)
+                    .cornerRadius(8)
+            }
         }
+        .padding()
     }
 }
 
```
