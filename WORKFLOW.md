echo "# Git Rescue Workflow Documentation

## 1. Bisect Finding
- **Commit Hash:** e680651 (or respective commit where regression entered)
- **Explanation:** Introduced a logic error in pricing calculations that returned NaN for orders.

## 2. Recommended Branching Strategy
- **Strategy:** GitHub Flow
- **Justification:** For a small team of 4 working on continuous delivery or features, GitHub Flow provides a lightweight, feature-branch-based workflow with pull requests and code reviews without the release overhead of Git Flow.

## 3. Secret Removal in History
- **Full Removal Steps:** Use \`git filter-repo\` or \`git filter-branch\` to completely scrub the .env file from all historical commits, followed by a force push.
- **Why Assignment Didn't Require It:** The assignment only required stopping tracking for active/future commits (\`git rm --cached\`), which prevents accidental exposure in current versions while keeping the exercise simple.

## 4. History Rewriting
- **Acceptability in Task 2:** Acceptable because the commits were strictly local and had not been shared or pulled by teammates yet.
- **Unacceptability on Shared Commits:** Rewriting history on shared branches alters commit hashes, causing divergence and breaking coworkers' local working states and pull workflows.
"