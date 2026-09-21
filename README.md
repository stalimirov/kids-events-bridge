# Bridge page — Занимания · София

Статична тест страница: 26 карти, три филтъра (възраст · район · категория), CTA = външен линк към организатора. Без booking, без бранд.

- `index.html` — страницата
- `thumbs/` — снимки на картите
- `og.png` / `post-thumb-1024.png` — FB preview

Публичният пост в групата чака Dimi GO. Линкът в поста е само с UTM отдолу.

## Live
- URL: https://kids-events-bridge-deploy.vercel.app
- Пост линк: https://kids-events-bridge-deploy.vercel.app/?utm_source=fb_group&utm_medium=social&utm_campaign=bridge_v1
- Repo: https://github.com/stalimirov/kids-events-bridge
- Analytics: [Vercel → kids-events-bridge-deploy → Analytics](https://vercel.com/stalimirovs-projects/kids-events-bridge-deploy/analytics)

## Какво мерим (1–2 седмици)

Тезата: FB пост → наша страница → клик към организатор (+ връщане).

Гледай **Analytics → Pages** (виртуални пътища). Hobby планът не дава custom-event dashboard, затова събитията са pageview-и.

| Приоритет | Сигнал | Path | Какво значи |
|-----------|--------|------|-------------|
| 1 | Посещение от поста | `/e/from/fb_group/bridge_v1` | някой е отворил линка с UTM |
| 1 | CTA към организатор | `/e/cta/{slug}` | клик на „към организатора“ |
| 2 | Филтър | `/e/filter/{age}/{area}/{cat}` | ползва рафта, не само скролва |
| 3 | Връщане | `/e/return` | втори visit (localStorage) |
| фон | Всяко посещение | `/` | включва директни, preview, теб |

**Успех:** има трафик от `/e/from/fb_group/bridge_v1` **и** CTA кликове. Без CTA — страницата се гледа, но не прехвърля към организатор.

**Фалшификатор (от тезата):** след 1–2 седмици с жив пост няма UTM посещения или няма CTA → не уголемяваме каталога.

**Не мерим:** записвания, приходи, DM, време на страница, bounce. Това не е conversion test към плащане.

Слаговете на CTA следват файла в `thumbs/` без номера, напр. `/e/cta/sway`, `/e/cta/yuki-art`.
