# FabSol Site (Next.js + NextAuth + Tailwind)

- **Framework**: Next.js (Pages Router)
- **Auth**: NextAuth.js (Naver provider)
- **UI**: TailwindCSS, Framer Motion, lucide-react
- **Deploy**: Vercel

## 1) Quick Start
```bash
npm i
npm run dev
```
Open http://localhost:3000

## 2) Environment Variables
Create `.env.local`:
```
NEXTAUTH_SECRET=replace-with-random-32-64chars
NAVER_CLIENT_ID=your-naver-client-id
NAVER_CLIENT_SECRET=your-naver-client-secret
# If not on Vercel, set this:
# NEXTAUTH_URL=http://localhost:3000
```

## 3) Naver Developers Console
- App type: 웹
- Callback URL(리다이렉트 URI):
  - `http://localhost:3000/api/auth/callback/naver` (local)
  - `https://YOURDOMAIN/api/auth/callback/naver` (prod)
- 권한: 이메일(profile) 필수 권한 요청

## 4) Deploy to Vercel
- Import repo → **Environment Variables**:
  - `NEXTAUTH_SECRET`, `NAVER_CLIENT_ID`, `NAVER_CLIENT_SECRET`
- Vercel에선 `NEXTAUTH_URL` 보통 불필요 (자동 설정). 필요 시 수동 지정.

## 5) Smart Store Links
- 주문 섹션은 다음 상품으로 딥링크:
  - https://smartstore.naver.com/fabsol/products/11785367210
  - https://smartstore.naver.com/fabsol/products/12013426571

## Notes
- This is a minimal, production-lean starter. Customize `components/FabSolLanding.tsx` for content.
- For admin-only pages, wrap with `useSession()` and `getSession()` guards.
