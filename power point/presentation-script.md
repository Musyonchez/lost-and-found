# Presentation Script — USIU Lost & Found

> Words in **"quotes"** are what you say out loud. Steps in `[ ]` are what you do on screen.

---

## Person 1 — Norman's Principle #6 (Design for Error) + Shneiderman's Rule #3 (Informative Feedback)

---

### Norman #6 — Design for Error

`[ Open the app. Click Sign In. ]`

"So the first principle I'm covering is Norman's Principle 6 — Design for Error. The idea is that users will always make mistakes, and the system should help them recover, not just crash or fail silently."

`[ Submit the login form completely empty. ]`

"If I try to log in without entering anything, the app doesn't just freeze — it immediately tells me exactly what went wrong. You can see the error message right there."

`[ Type a wrong password and submit. ]`

"Same here — wrong credentials, clear message. The user knows what happened and what to do next."

`[ Close AuthModal. Click Report Item. ]`

"Same principle in the Report Item form. Every required field is marked with an asterisk. If I try to submit without filling them in, the browser blocks it and highlights what's missing."

`[ Open a claim modal on an item that already has an approved claim. ]`

"And here's where it gets interesting — if a claim has already been approved on this item, the form doesn't just sit there and let you submit blindly. It replaces itself with a read-only view showing the approved claimant's details. The system adapted based on state — that's Design for Error."

"Key takeaway: this app never fails silently. Every mistake produces a clear, helpful response."

---

### Shneiderman #3 — Informative Feedback

`[ Go back to the homepage item feed. ]`

"Now Rule 3 from Shneiderman — Informative Feedback. Every action should produce a visible, meaningful response so the user knows their action registered."

`[ Point to a card that has a claim count badge next to the button. ]`

"Look at this badge next to the Claim button — it shows how many claims have already been submitted on this item. That number updates in real time after every claim. The user doesn't need to guess whether their action worked."

`[ Click the notification bell in the navbar. ]`

"The notification bell here — the red number on it is the unread count. As new notifications come in, that number updates. You always know at a glance whether something needs your attention."

`[ Close bell. Open Report Item, fill it in quickly, submit. ]`

"When I submit a report, a toast pops up in the corner — 'Report submitted. An admin will review it.' That's confirmation the action went through. Not a page reload, not silence — a clear, immediate response."

`[ Log in as admin. Go to Admin Dashboard. Expand claims on an item. ]`

"And in the Admin Dashboard, every claim has a status badge — yellow for Pending, green for Approved, red for Denied. Every state change is communicated visually. The admin never has to guess what's happened to a claim."

---

## Person 2 — Norman's Principle #3 (Make Things Visible) + Shneiderman's Rule #8 (Reduce Memory Load)

---

### Norman #3 — Make Things Visible

`[ Show the homepage logged in. Point to the navbar. ]`

"Norman's Principle 3 is about visibility — controls and system state should always be visible so users know what they can do and where things stand."

"Look at the navbar. Report Lost and Report Found are always there. Users never have to hunt for how to add an item — the action is always in front of them."

`[ Point to an item card on the feed. ]`

"Now look at these item cards. Every card shows the status badge, the category, the date, the location, and the claim count — all without clicking anything. Nothing important is hidden behind extra clicks."

`[ Log in as admin and open the Admin Dashboard. ]`

"In the Admin Dashboard, the full claim history for each item is expandable right in-place. Admins don't navigate away to a separate page — everything is here, visible, on one screen."

`[ Point to the notification bell badge. ]`

"And the notification bell badge is always visible in the navbar. Even while you're browsing the feed, you can see at a glance if something is waiting for your attention. You never miss an update."

---

### Shneiderman #8 — Reduce Memory Load

`[ Show the search bar and filter tabs on the homepage. ]`

"Rule 8 is Reduce Memory Load — recognition over recall. Users shouldn't have to remember information from one screen to use another."

"These filters — category, status — are presented as visible dropdowns and buttons. The user doesn't type from memory, they pick from what they can see."

`[ Point to a full item card. ]`

"Every card shows the image, name, category, location, date, and status right there. The user never needs to click into an item just to remember what it was. Everything they need to make a decision is on the surface."

`[ Open a ClaimItemModal on an item with an approved claim. ]`

"And here — when a claim has been approved, the modal shows the claimant's name, contact, and description right there in a panel. The admin or reporter never needs to remember who claimed what. The system holds that information for them."

---

## Person 3 — Shneiderman's Rule #1 (Consistency) + Norman's Principle #5 (Exploit Constraints)

---

### Shneiderman #1 — Consistency

`[ Open the Report Item modal, then close it. Open the Claim modal. ]`

"Rule 1 is Consistency — similar operations should behave the same way throughout the interface. Let me show you."

"Both these modals follow the exact same layout pattern. Title at the top, form fields in the middle, action buttons at the bottom. Once you've used one modal, you know how to use all of them."

`[ Point to button colors on the homepage and inside modals. ]`

"Colour language is consistent across the whole app. Red means lost or destructive action. Green means found or confirm. Grey means cancel. You learn this once and it applies everywhere."

`[ Point to multiple item cards — lost and found. ]`

"Whether an item is lost or found, the card layout is identical. Same badge position, same button placement, same information order. Consistency means users build muscle memory — they don't have to re-learn each screen."

`[ Open Admin Dashboard, point to status badges. ]`

"The status badge colours — yellow for Pending, green for Approved or Verified, red for Denied or Lost — are the same in item cards, in the claim list, and in the admin dashboard. One visual language across the whole system."

---

### Norman #5 — Exploit Constraints

`[ Click 'Report Lost' button. Show the modal with type pre-set. ]`

"Norman's Principle 5 is Exploit Constraints — design it so wrong actions are impossible, not just discouraged."

"When you click Report Lost, the form opens with type pre-locked to 'Lost'. You can't accidentally change it mid-form. The constraint is physical — the field isn't editable."

`[ Log in as admin. Go to Admin Dashboard. Expand claims. Point to approve/deny buttons on an already-approved claim. ]`

"Once a claim is approved or denied, the approve and deny buttons disappear for that claim. You literally cannot double-approve. The wrong action has been removed from the interface."

`[ Open a ClaimItemModal on an approved item. ]`

"After approval, the form is completely replaced with a read-only panel. There are no input fields left to misuse. The constraint is structural."

`[ Open Report Item. Try to upload a non-image file. ]`

"And file upload — the input only accepts image file types. You are physically constrained from uploading a PDF or the wrong file type. The system prevents the mistake before it happens."

---

## Person 4 — Authentication & Navigation

`[ Make sure you are logged out. Open the homepage. ]`

"I'm going to walk you through how the app handles authentication and navigation. Let's start from the beginning — a visitor who isn't logged in."

"This is what you see when you arrive. The item feed is fully visible — you can browse and search. But notice: there's no Report button, no notification bell, no dashboard link. That's intentional access control. You can look, but you can't act without an account."

`[ Click Sign In. ]`

"Clicking Sign In opens this modal. You can toggle between Login and Register right here — no page navigation needed. For registration you enter your name, email, an optional phone number for SMS notifications, and a password."

`[ Register or log in. ]`

"After logging in, watch the navbar change. The user's name appears, the notification bell appears, and the Report Lost and Report Found buttons appear. The entire UI responds to authentication state — it's not just a gate, it actively changes what's available."

`[ Type in the search bar and show items filtering. ]`

"The search bar filters in real time as you type. Clear it — all items come back. This is non-destructive filtering. Nothing is deleted, nothing is hidden permanently."

`[ Use the category or status filter. ]`

"Same with these filter tabs — switch between Lost, Found, All. The results update instantly. Every filter is reversible."

`[ Click the user dropdown and log out. ]`

"Logging out returns the navbar to its visitor state. The bell disappears, the report buttons disappear, the feed stays visible. Clean, predictable state management."

---

## Person 5 — Reporting & Claiming

`[ Make sure you are logged in. ]`

"Let me walk you through the two main user flows — reporting an item and claiming one."

`[ Click Report Lost. ]`

"Clicking Report Lost opens the modal pre-set to type Lost. Walk through the fields — title, description, category, location, date — and notice the form is split into two sections: 'What is the item?' and 'Where and when?' That grouping reduces cognitive load. You process one chunk at a time."

`[ Upload an image. Show the preview. ]`

"After uploading an image, a preview appears immediately. You know the upload worked without having to submit the form first."

`[ Close. Click Report Found. ]`

"Report Found opens the exact same modal, but pre-set to Found. Same layout, same fields, same flow. Consistency."

`[ Close. Point to item cards on the feed. ]`

"Now look at the item cards. Each one shows the status badge, category, location, date, reporter name, and the claim count badge right on the button. All the information you need to decide whether to claim — visible without clicking in."

`[ Click Claim or Found It on an item with existing claims. ]`

"When I open this claim form, notice the yellow notice at the top — it says other claims have already been submitted, but I can still submit mine. The admin reviews all of them. Transparent and fair."

`[ Fill in the form and submit. ]`

"After submitting, a toast confirms my claim went through. The claim count on the card updates. My action had a visible result."

`[ Find an item with an approved claim and open its modal. ]`

"Now look at this item where a claim has already been approved. Instead of a form, I see a read-only panel with the approved claimant's name, contact, and description. No form to misuse. The system tells me exactly what the status is."

---

## Person 6 — Admin Dashboard, Notifications & Full Flow

`[ Log out. Log in as the admin account. ]`

"Let me show you the admin side of the system. After logging in as admin, notice the navbar gains a shield icon — that's the link to the Admin Dashboard."

`[ Click the Admin Dashboard link. ]`

"This is the dashboard. All reported items are listed here. At the top you've got summary stats — total, pending, verified, matched, resolved. The filter defaults to Pending so the admin immediately sees what needs action."

`[ Point to an item with claims. Click 'View Claims'. ]`

"Each item has a View Claims toggle. Clicking it expands the claim list right in-place — no navigation away, no new page. Each claim shows the claimant's name, contact details, their description, and a status badge."

`[ Click Approve on a pending claim. Show the confirmation dialog. ]`

"Clicking Approve opens a confirmation dialog. It explicitly tells the admin that approving this claim will auto-deny all other pending claims on this item. That's Design for Error — no accidental approvals."

`[ Confirm the approval. ]`

"After confirming — the approved claim turns green, the others turn red immediately. The feedback is instant and unambiguous."

`[ Click Deny on another claim. Show the dialog. Confirm. ]`

"Denying works the same way — confirmation first, then immediate visual feedback."

`[ Show the status update on an item — change it from verified to resolved. ]`

"Items also have their own status flow — from Pending to Verified to Matched to Resolved. Each step maps to where the item is in the recovery process. Pending means under review, Verified means it's live on the feed, Matched means an owner has been identified, Resolved means it's been physically returned."

`[ Click the notification bell. ]`

"Finally — the notification bell. Click it and you see the notification list. Unread notifications are highlighted."

`[ Click 'Mark all read'. Show the badge disappear. ]`

"Mark all read — the badge disappears. The system confirms all notifications have been acknowledged."

`[ Delete one notification. ]`

"You can also delete individual notifications to keep the list clean."

"Admins receive notifications for every new report submitted and every claim received. Regular users receive notifications when their claim is approved or denied, and when their reported item's status changes. It's a closed feedback loop — every action in the system produces a notification for the right person."

---

> **Tips before presenting:**
> - Do a full run-through once before the real thing
> - Keep the browser window large — audience needs to see clearly
> - Don't rush transitions — pause after each action so the audience sees the result
> - If something doesn't load, say "in a live environment this would..." and move on
> - Each person should know their own section cold and be ready to hand over smoothly
