---
title: "Update ContentView.swift"
description: "Auto-generated from PR #9"
---

**PR:** [#9](https://github.com/Rita-Tavares/Demo-HelloWorld/pull/9)

### Summary
- This page was generated automatically when the PR merged.

### Swift Code changes (unified diff)

```swift
diff --git a/Sources/ContentView.swift b/Sources/ContentView.swift
index 618aeba..9043171 100644
--- a/Sources/ContentView.swift
+++ b/Sources/ContentView.swift
@@ -2,27 +2,58 @@ import SwiftUI
 
 struct ContentView: View {
     @State private var counter = 0
+    @State private var isOn = false
 
     var body: some View {
-        VStack(spacing: 20) {
+        VStack(spacing: 16) {
             Text("Welcome to HelloWorld App")
                 .font(.largeTitle)
                 .multilineTextAlignment(.center)
 
-            Text("You've tapped \(counter) times")
-                .font(.headline)
+            // Counter section
+            HStack(spacing: 12) {
+                Button("-") { counter = max(0, counter - 1) }
+                    .buttonStyle(.bordered)
+                Text("\(counter)")
+                    .font(.title2)
+                    .monospacedDigit()
+                    .frame(minWidth: 44)
+                Button("+") { counter += 1 }
+                    .buttonStyle(.borderedProminent)
+            }
+
+            // Toggle section
+            Toggle(isOn: $isOn) {
+                Text("Enable Pro Mode")
+            }
+            .padding(.horizontal)
 
-            Button(action: {
-                counter += 1
-            }) {
-                Text("Tap me")
-                    .padding()
-                    .background(Color.blue)
-                    .foregroundColor(.white)
-                    .cornerRadius(8)
+            if isOn {
+                ProModeCard(counter: counter)
+                    .transition(.opacity)
             }
         }
         .padding()
+        .animation(.default, value: isOn)
+    }
+}
+
+struct ProModeCard: View {
+    let counter: Int
+
+    var body: some View {
+        VStack(spacing: 8) {
+            Text("Pro Mode")
+                .font(.headline)
+            Text("Current counter: \(counter)")
+                .font(.subheadline)
+        }
+        .padding()
+        .frame(maxWidth: .infinity)
+        .background(Color(.secondarySystemBackground))
+        .clipShape(RoundedRectangle(cornerRadius: 12))
+        .shadow(radius: 1)
+        .padding(.horizontal)
     }
 }
 
```
