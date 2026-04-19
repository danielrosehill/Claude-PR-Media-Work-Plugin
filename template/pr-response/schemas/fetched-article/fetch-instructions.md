# Fetching Instructions

You should fetch the URL that you have been invoked to fetch by creating a JSON representation with the following key value pairs:

## Article Parameters

title: Title of the article exactly as it appeared 
subtitle: Subtitle or subheadling, if any  
pub_name: The name of the publication or website, for example: "The Economist"
article_url: The URL of the article
main_author_name: Name of the author
coauthor_1: Name of the first coauthor. Leave blank if one author.
main_author_title: Provided title for the main author. For example: "Head Of Regional News." 
main_author_bio_provided: Provided biography of the main author (that appeared on the website).
main_author_bio_enriched: Provide a short biography for the main author.
main_author_ai_summary: Generate an AI summary of the journalist or author's background. This should be a short summary covering their expertise, notable work, career highlights, and areas of focus. Research the author if needed to provide context beyond what's in the article itself.
author_previous_commentary: Has the author written about this theme previously? If so, what viewpoints has the author articulated about this subject? Note: Only research and populate this field if the author is NOT the subject of the media monitoring (check CLAUDE.md to determine who the subject is). If the author is the subject, leave blank or note "N/A - author is subject".
pub_summary: A short one sentence publication of the summary. For example: "Widely read international business periodical with an estimated daily circ of 200M, published in print and digital."
pub_leaning: A short description of the publication's general editorial bias or leaning. For example: "Leans center right; associated with Republican Party"

## Article Body Text

full_text: the full text of the article with all non-text elements removed. Omit captions. 
article_word_count: The computed word count of the full text (Integer)

## Summarisation

claude_summary: A one paragraph summary outlining the main argument of the article 

## Type Identification

is_coverage: Is this third party coverage of the subject of the media monitoring? (Boolean)

is_oped: Is this an opinion piece written by the subject of the media monitoring such as an op ed or contributed content?  (Boolean)

by_subject: Was this article written by the subject of the media monitoring? To determine this, check the CLAUDE.md file in the repository root to identify who the subject is (if anyone), then compare with the article's author. (Boolean)

## Reaction

has_comments: Did you see a comments section? Boolean. If so, yes.  (Boolean)

comment_summary: Provide a summary of the reaction to the article in the comments section focusing on recurrent reader responses. You may wish to quote verbatim to highlight common opinions, supportive or otherwise. 

comments_supportive: On a scale of 1 to 10, how supportive would you rank the comments section as being of the author's thesis (integer)

comment_count: Can you identify a comments count? If so, what is it? (Integer)

## Tagging

keywords: Provide 5 tags for the articles in JSON. The tags should capture recurring points.

## Display Summary

display_summary: Generate a displayable summary of the coverage following this format: "An op-ed published in The Economist on 17th Oct 2025 by Joe Blogs. Blogs argued that bipartisan support is needed for this initiative drawing upon the recent election in Greece as support. A lively comments section ensued (at time of capture, 200 comments). Most comments were supportive but common criticisms included that the comparison was fundamentally flawed with one commenter putting it bluntly: "Yeah - different continent buddy". 800 words.