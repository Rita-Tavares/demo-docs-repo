---
title: "Update Calculator.swift"
description: "Auto-generated from PR #7"
---

**PR:** [#7](https://github.com/Rita-Tavares/Demo-HelloWorld/pull/7)

### Summary
- This page was generated automatically when the PR merged.

### Swift Code changes (unified diff)

```swift
diff --git a/Sources/Calculator.swift b/Sources/Calculator.swift
index 7c7f9f1..2944dc4 100644
--- a/Sources/Calculator.swift
+++ b/Sources/Calculator.swift
@@ -1,8 +1,15 @@
 public struct Calculator {
     public init() {}
 
-    // Adds two numbers.
+    // Adds two numbers (now clamps result at 0..1_000_000)
     public func add(_ a: Int, _ b: Int) -> Int {
-        return a + b
+        let sum = a + b
+        return max(0, min(sum, 1_000_000))
+    }
+
+    // NEW: Multiply two numbers (safe clamp)
+    public func multiply(_ a: Int, _ b: Int) -> Int {
+        let product = a * b
+        return max(0, min(product, 1_000_000))
     }
 }
```
