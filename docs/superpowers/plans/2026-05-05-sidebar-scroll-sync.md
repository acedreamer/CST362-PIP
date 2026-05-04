# Sidebar Scroll Synchronization Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Synchronize the sidebar's scroll position with the main content scroll to ensure the active navigation link is always visible.

**Architecture:** Modify the `updateSidebarActiveLink` function in `app.js` to trigger a `scrollIntoView` call on the active link within the scrollable sidebar container.

**Tech Stack:** Vanilla JavaScript.

---

### Task 1: Update Sidebar Active Link Logic

**Files:**
- Modify: `ExamWiki/app.js:100-115`

- [ ] **Step 1: Modify `updateSidebarActiveLink` to include scroll logic**

Update the function to identify the active link and call `scrollIntoView` on it.

```javascript
function updateSidebarActiveLink(activeTopicId) {
  const links = document.querySelectorAll('.sidebar-topic-link');
  const modules = document.querySelectorAll('.sidebar-module');

  links.forEach(link => {
    if (link.getAttribute('data-topic-id') === activeTopicId) {
      link.classList.add('active');
      const parentModule = link.closest('.sidebar-module');
      modules.forEach(m => m.classList.remove('active'));
      parentModule.classList.add('active');
      
      // FIX: Scroll the sidebar to keep the active link in view
      link.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
    } else {
      link.classList.remove('active');
    }
  });
}
```

- [ ] **Step 2: Verify the logic manually**

Since there are no automated tests for the UI scroll behavior in this project, verification will be based on code review and manual confirmation of the implementation.

- [ ] **Step 3: Commit the change**

```bash
git add ExamWiki/app.js
git commit -m "fix: synchronize sidebar scroll with main content"
```
