# National University of Singapore (NUS) · usability audit · 2026-11-02

Pages read: home https://www.nus.edu.sg/ (bot_check_page, HTTP 200, 346 ms, 0 KB) ·
admissions https://www.nus.edu.sg/admissions (ok, HTTP 200, 1668 ms, 45 KB)
robots.txt: answered with an HTML page, not a rules file, so no rules apply.

## Heuristics

| # | Heuristic | Severity | Evidence from the HTML |
|---|---|---|---|
| 1 | Visibility of system status | 1 | `admissions:breadcrumbs.present` = true; `admissions:title` = "NUS - Admissions"; `admissions:navigation.aria_current_count` = 0 (the menu does not mark the section you are in); `admissions:http.response_ms` = 1668 |
| 2 | Match between system and the real world | 1 | `admissions:navigation.landmarks.0.top_level_links` = ["Home", "Admissions", "Education", "Research", "Sustainability", "News", "Giving", "About"] (plain words); `admissions:headings.h1` = ["Programmes"] (the page is titled "Admissions" but its main heading says "Programmes"); `admissions:headings.h2` = ["Sidebar", "Scholarships", "Financial aid", "Shape Your Future", "Staying on campus", "Apply"] ("Sidebar" describes layout, not content) |
| 3 | User control and freedom | 0 | `admissions:breadcrumbs.present` = true; `admissions:carousel_or_slider_hints` = 0; `admissions:autoplay_media` = 0 (nothing moves on its own on this page) |
| 4 | Consistency and standards | 3 | `admissions:lang` = null; `admissions:landmarks.main` = false; `admissions:images.missing_alt` = 3; `admissions:links.empty_text` = 11; `admissions:headings.h1_count` = 1 |
| 5 | Error prevention | 1 | `admissions:forms.forms` = 2; `admissions:forms.inputs` = 1; `admissions:forms.inputs_without_label` = 1; `admissions:forms.unlabelled_with_placeholder_only` = 1 (the only text field, most likely the search box, has a placeholder but no label) |
| 6 | Recognition rather than recall | 1 | `admissions:navigation.landmarks.0.top_level_link_count` = 8; `admissions:links.vague_text_total` = 2 ("read more" and "learn more"); `admissions:search.search_input` = true |
| 7 | Flexibility and efficiency of use | 2 | `admissions:skip_link.present` = false; `admissions:navigation.landmarks.0.links` = 63; `admissions:search.search_form` = true; `admissions:http.response_ms` = 1668; `admissions:http.bytes` = 45654; `admissions:meta_viewport` = "width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" (this setting stops visitors zooming in) |
| 8 | Aesthetic and minimalist design | not judged | not judged from HTML: the layout cannot be seen. A human should look at the page, which has `admissions:visible_word_count` = 574 and `admissions:headings.h2_count` = 6 |
| 9 | Help users recognise, diagnose and recover from errors | not judged | not judged from HTML: no error state is shown on the page; `admissions:forms.inputs_without_label` = 1 |
| 10 | Help and documentation | 1 | `admissions:help_faq_contact_links` = ["Contact us"] (no FAQ link); `admissions:footer_contact.phone_pattern` = true; `admissions:footer_contact.postal_address_pattern` = true |

Severity: 0 no problem, 1 cosmetic, 2 minor, 3 major, 4 severe (see HEURISTICS.md). Lower is better.

## Three suggestions for the web team
These suggestions rest on the admissions page only; the home page answered with a bot-check page
(`home:outcome` = "bot_check_page") and was not judged.
1. **The page language and image text on the admissions page · Consistency and standards.** The `<html>` element
   has no language (`lang` = null), 3 images have no `alt` attribute and 11 links have no text. Set `lang="en"`,
   give each image an `alt` (empty if only decorative) and give each icon-only link a name, so screen readers read the page correctly.
2. **The page zoom setting · Flexibility and efficiency of use.** The viewport setting contains
   `user-scalable=no` and `maximum-scale=1.0`, which stops visitors zooming in. Remove both so people who need larger text can use pinch-zoom.
   Please also add a "Skip to content" link and a `<main>` element before the 63-link menu.
3. **The main heading and the "Sidebar" heading · Match between system and the real world.** The page is titled
   "Admissions" but its only `<h1>` says "Programmes", and one `<h2>` reads "Sidebar". Change the main heading to
   "Admissions" and give the sidebar a heading that names what it holds.

## Since last week
Last week both pages answered with a bot-check page and all ten rows were not judged. This week the admissions page
answered with its content (`outcome` went from "bot_check_page" to "ok"), so 8 rows now have scores (total severity 10).
The home page still answered with a bot-check page. Response time of the home page was 346 ms (last week 596 ms).

## Limits
Judged from the HTML of two pages only. Visual design, colour contrast and real tasks were not judged.
These findings are prompts for a human evaluator, not verdicts.
