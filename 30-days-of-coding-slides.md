---
marp: true
theme: default
paginate: true
---

<!-- _class: lead -->

# 30 Days of Coding in Unity  
### Intro & Days 1–2

- Daily 20–40 minute coding exercises
- Focus: **C# + Unity fundamentals**
- Small, focused scripts that build confidence
- You can:
  - Copy/paste the examples
  - Experiment by tweaking values
  - Ask: *“What happens if…?”*

---

# Day 1 – First Script & Console Output

**Goal:**  
Create your first C# script, attach it to a GameObject, and see output in the Console.

**Tasks:**

1. Create a new script called `HelloUnity.cs`
2. Attach it to any GameObject in your scene
3. In `Start()`, print a welcome message
4. In `Update()`, print a simple counter every frame

```csharp
using UnityEngine;

public class HelloUnity : MonoBehaviour
{
    int frameCount = 0;

    void Start()
    {
        Debug.Log("Hello Unity! 30 days of coding starts now.");
    }

    void Update()
    {
        frameCount++;
        Debug.Log($"Frame: {frameCount}");
    }
}
```

*Tags: `Debug.Log` `Update` `fundamentals`*

---

# Day 2 – Toggle Controls

**Goal:**  
Use a key press to toggle a boolean value and react only when it changes.

**Tasks:**

1. Create a script called `ToggleSwitch.cs`
2. Create and initialise:
   - `bool isActive`
   - `bool previousIsActive`
3. In `Update()`:
   - When **Space** is pressed, flip `isActive`
   - Check if `isActive` has changed since last frame
   - Log a message *only when the value changes*
   - Update `previousIsActive` to match `isActive`

```csharp
using UnityEngine;

public class ToggleSwitch : MonoBehaviour
{
    public bool isActive = false;
    bool previousIsActive = false;

    void Update()
    {
        // Flip isActive when Space is pressed
        if (Input.GetKeyDown(KeyCode.Space))
        {
            isActive = !isActive;
        }

        // Has the value changed since last frame?
        if (isActive != previousIsActive)
        {
            Debug.Log($"Toggle state changed: {isActive}");
            previousIsActive = isActive;
        }
    }
}
```

> Hint: Don’t worry if it feels like you have **lots of `if` statements** at this stage —  
> learning to express logic clearly is the priority.

*Tags: `Input` `conditionals` `booleans`*
