# Mailchimp email template

`newsletter.html` is a responsive, table-based HTML email built for Mailchimp's
**Code your own** template editor. It renders correctly in Gmail, Apple Mail,
Outlook (desktop and web), and on mobile.

## Upload to Mailchimp

1. Mailchimp → **Content** → **Email templates** → **Create template** → **Code your own** → **Import HTML**.
2. Upload `newsletter.html` (or paste the code) and save.
3. When creating a campaign, pick this template under **Saved templates**.
4. Set the **Subject line** and **Preview text** in the campaign. The template picks them up through `*|MC:SUBJECT|*` and `*|MC_PREVIEW_TEXT|*`.

## Before sending

- **Logo and images:** the `placehold.co` images are placeholders. Upload real images
  in Mailchimp's Content Studio and replace each `src`. Hero image: 1200×560 px.
  Feature images: 500×320 px. Always give images `alt` text.
- **Links:** every button and link points to `https://www.mynica.com`. Change them to
  the pages you want.
- **Social links:** update the LinkedIn/Facebook URLs in the footer, or delete the ones you don't use.
- **Mailing address:** the footer pulls it from your audience settings (`*|HTML:LIST_ADDRESS_HTML|*`).
  The law requires it, so leave it in.

## Editing in Mailchimp

| Region | What you can do in the editor |
| --- | --- |
| `header_logo`, `hero_image`, `hero_copy`, `section_heading`, `feature_left`, `feature_right`, `callout`, `signoff`, `footer_social` | Edit text and images (`mc:edit`) |
| Two-column feature row | Duplicate it with the repeat control (`mc:repeatable`) |
| Hero image, "Have a question?" callout | Hide it for a single campaign (`mc:hideable`) |

To change the primary **Learn More** button, edit the code. It uses Outlook VML so it
renders as a real button in Outlook, and the visual editor can break that markup. Its
link and label appear twice: once inside `<v:roundrect>` and once in the `<a>` tag. Change both.

## Brand colors

Find and replace these hex values to match the brand:

| Color | Use |
| --- | --- |
| `#0B2545` | Headings, dark callout background |
| `#1E6FD9` | Buttons, links, eyebrow text |
| `#344054` / `#475467` | Body text |
| `#F2F4F7` | Page background |

## Merge tags used

`*|FNAME|*` (the greeting falls back to "there" when the first name is empty), `*|ARCHIVE|*`,
`*|UPDATE_PROFILE|*`, `*|UNSUB|*`, `*|CURRENT_YEAR|*`, `*|LIST:COMPANY|*`,
`*|LIST:DESCRIPTION|*`, `*|HTML:LIST_ADDRESS_HTML|*`, `*|HTML:REWARDS|*`.

## Fall member check-in (`fall-member-checkin.html`)

A one-off letter from NICA's founder thanking members and asking for feedback. It has no
images, so nothing needs uploading. The fall look comes from colored stripes and emoji.
Upload it the same way as the newsletter. Before sending:

- Replace `[Founder's Name]` in the signature.
- Make sure the campaign's **Reply-to** address is the inbox where you want member ideas to arrive.
- Optional: swap the "NICA" text wordmark in the header for your logo image (instructions are in the code comment).

Colors: NICA navy `#0B2E59`, light blue `#EEF3FA` / `#A9C4E8`. Fall accents: `#8C2F1B`, `#C4561B`, `#E08A2E`, `#D9A93A`.
Page background: `#F6EEE3`.
