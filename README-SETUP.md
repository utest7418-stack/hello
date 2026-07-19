TEJAS LIBRARY — GALLERY ADMIN SETUP (Hinglish)
=================================================

ISME KYA HAI:
- index.html          → tera updated website (gallery ab dynamic hai)
- admin.html           → admin panel (yahan se photo/video link change karega)
- gallery-config.json  → gallery ka data (admin panel isi file ko update karta hai)
- images/              → apni images yahan daal sakta hai (optional, ya seedha external link bhi chalega jaise Google Drive/Imgur ka direct link)


STEP 1 — Files upload karo
---------------------------
Sab files (index.html, admin.html, gallery-config.json, images folder) apne
GitHub repo ke ROOT me daal do, jaha pehle se index.html tha usko REPLACE kar do.


STEP 2 — GitHub token banao (admin panel ke liye)
---------------------------------------------------
1. GitHub.com pe login karo
2. Settings → Developer settings → Personal access tokens → Fine-grained tokens
3. "Generate new token" pe click karo
4. Repository access → "Only select repositories" → apni repo choose karo
5. Permissions → "Repository permissions" → Contents → "Read and write" select karo
6. Generate token → COPY kar lo (ye sirf ek baar dikhega, safe jagah rakh lo,
   ya har baar admin panel me naya generate kar sakta hai)

IMPORTANT: Ye token teri repo me likhne ki permission deta hai. Kabhi bhi
kisi ko mat bhejo, aur admin.html ka link kisi ko share mat karo.


STEP 3 — Admin panel use karo
-------------------------------
1. apni site pe jaake  yoursite.com/admin.html  kholo
2. Password daalo (default: tejas@2026 — ise change karna zaroori hai, niche dekho)
3. GitHub Username, Repo Name, aur Token daal ke "Load Gallery Slots" dabao
4. 10 slots dikhenge — har slot me:
   - URL box: image ya video ka direct link
   - Image/Video dropdown
   - "On" checkbox: uncheck karega to wo slot gallery me show nahi hoga
5. Jitne chahiye utne slots ON rakho (baaki OFF), URL daal ke
6. Neeche "Save to GitHub" dabao
7. 1-2 min me live site pe changes dikhne lagenge (GitHub Pages thoda cache karta hai)


PASSWORD CHANGE KAISE KARE:
-----------------------------
admin.html file kholo, is line ko dhoondo (near top of <script> tag):

    const ADMIN_PASSWORD = "tejas@2026";

"tejas@2026" ki jagah apna naya password likh do aur file wapas GitHub pe upload
kar do.


IMAGE/VIDEO URL KAHA SE LAAYE:
--------------------------------
- Sabse simple: image ko apni repo ke "images" folder me upload kar do, aur URL me
  likho:  images/photo1.jpg
- Ya kisi bhi image hosting (Imgur, GitHub raw link, etc.) ka DIRECT link use karo
  (link jo seedha .jpg/.png/.mp4 pe khatam ho, koi preview page nahi)


NOTE:
------
- Ye poora setup FREE hai, koi paid service nahi lagti
- Static hosting (GitHub Pages) pe hi chal jaayega, koi server nahi chahiye
- Password protection sirf casual hai (real security nahi) — asli suraksha
  GitHub token se aati hai jo sirf tere paas hai
