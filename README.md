# ASTRA OS

Internal workspace for research institute managing NEXUS (UAV) and VAWT (wind turbine) programs.

## Quick Start

```bash
# 1. Clone and install
cd astra-os
npm install

# 2. Set up Firebase
# - Go to https://console.firebase.google.com/
# - Create project → Add web app → copy config
# - Rename .env.example to .env.local and fill in values
# - Enable Email/Password auth in Firebase Console → Authentication → Sign-in method
# - Create Firestore database (start in test mode, then deploy rules below)

# 3. Run locally
npm run dev
# Open http://localhost:3000

# 4. Deploy to Vercel
# - Push to GitHub
# - Connect repo at https://vercel.com
# - Add environment variables in Vercel dashboard
```

## Firebase Setup Checklist

- [ ] Create Firebase project
- [ ] Register web app, copy config to .env.local
- [ ] Enable Authentication → Email/Password provider
- [ ] Create Cloud Firestore database
- [ ] Deploy security rules (see firestore.rules in this repo)
- [ ] (Optional) Set up Resend for email notifications

## Project Structure

```
src/
  app/                 # Next.js App Router pages
    (auth)/login       # Login/signup page
    (dashboard)/       # Protected routes with sidebar
      page.tsx         # Dashboard home
      research/        # Research Pipeline
      projects/        # Projects hub
      meetings/        # Meetings & calendar
      knowledge/       # Knowledge Base (placeholder)
      patents/         # Patent/IP (placeholder)
      people/          # Team directory (placeholder)
      equipment/       # Equipment tracking (placeholder)
      budget/          # Budget tracking (placeholder)
  components/
    ui/                # shadcn/ui components
    layout/            # Sidebar, Header
  hooks/
    useAuth.tsx        # Firebase auth context
    useFirestore.ts    # Real-time Firestore hooks
  lib/
    firebase.ts        # Firebase config
    utils.ts           # Helper functions
  types/
    index.ts           # TypeScript interfaces
```

## Features Implemented

- [x] Firebase Authentication (email/password)
- [x] Real-time Firestore data sync
- [x] Dashboard with stats, urgent deadlines, upcoming meetings
- [x] Research Pipeline (Kanban board + list view)
- [x] Paper detail page with editable form + notes log
- [x] Projects overview (gallery cards)
- [x] Meetings scheduler
- [x] Dark mode toggle
- [x] Mobile responsive sidebar
- [x] Role-based access control (admin/researcher)

## Next Steps (Your Team)

1. **Day 1**: Set up Firebase, run locally, create first project + paper
2. **Day 2**: Add drag-and-drop to Kanban (@dnd-kit already installed)
3. **Day 3**: Build Project detail page (milestones, notes, linked papers)
4. **Day 4**: Add FullCalendar to Meetings module
5. **Day 5**: Deploy to Vercel, invite team

## Tech Stack

- Next.js 15 + React 19 + TypeScript
- Tailwind CSS + shadcn/ui
- Firebase (Auth + Firestore + Storage)
- Vercel (hosting)
