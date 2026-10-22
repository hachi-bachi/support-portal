# Developer handoff notes

## What I delivered
I created a small static customer support page for Northstar Services. It consists of index.html, styles.css, a .gitignore, and an updated README. The page shows the support email, the support hours (Monday through Friday, 9 a.m. to 5 p.m. Central Time), and a styled layout with a gray background and a centered white content box. In response to the order status requirement, I added a reminder asking customers to include their order number when contacting support, and a Frequently asked questions section that answers "How can I check my order status?" by telling customers to sign in and open the Orders page. I also added support-checklist.md, which lists the checks for this requirement. The initial page and the FAQ requirement were committed separately.

## How I verified the page
I opened index.html in a browser and went through each item in support-checklist.md:
- Contact email is visible: passed, support@example.com appears as a link.
- Support hours specify Central Time: passed.
- Customers are asked to include their order number: passed, the reminder appears under the support hours.
- The FAQ explains where to find order status: passed, the question and answer appear in the new section.
- The page remains readable in a narrow browser window: passed, the text wraps and stays readable when the window is resized.
My default browser did not load styles.css, so the page looked unstyled there. I opened the same file in Safari, where the styling loaded correctly, and confirmed the CSS file contents and the link tag were correct.

## Remote change I received
A teammate's change was simulated by editing README.md directly on GitHub. It added a "Support escalation" section saying to escalate unresolved billing requests to the billing team after one business day, committed to main with the message "Document billing escalation process". My local README did not have this section until I ran git pull --ff-only origin main. The pull fast-forwarded my local main branch, and the escalation section then appeared in my local README and the commit appeared in git log.

## Git workflow explanation
git commit only saves a snapshot to my local repository on my computer. GitHub is a separate remote copy, so it does not change until I run git push origin main to send the local commits to it. I saw this after my first commit: git log showed the new commit locally, but the GitHub page still showed only the old README until I pushed. Pulling works the same way in the other direction, since my local files do not change when someone edits the remote until I run git pull.