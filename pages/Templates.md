- {{query (and (property template) (not [[Templates]]) )) }}
  query-table:: false
- These templates create tasks specific to my habits
	- Housework Todo
	  template:: htd
	  template-including-parent:: false
		- TODO - #housework
		  deadline::
	- TODO - #housework do some stuff
	  deadline:: [[Jun 16th, 2022]]
	-
- Still struggling figuring out how to use templates.   Here's a workflow for using templates to keep track of read books, but I'm still not able to get it to work: https://discuss.logseq.com/t/book-framework-setup-in-logseq-v1-2021/4324
-
- This "crumbs" template is a way to structure entry of a "thing" that you might want to check out later
	- template:: crumbs
	  template-including-parent:: false
	  publisher::
	  type::
	  link::
	  tags::
-
- This template captures everything I might need for a book
	- Book
	  template:: Book
	  template-including-parent:: false
		- title:: 
		  author::
		  status:: 
		  type:: #book
		  format::
		  year::
		  acquired:: 
		  topics::
		  genre::
		  tags::
		  icon:: 📖
		  url::
		  recommendedBy::
		  start::
		  finish::
		  rating:: ⭐️
		  digested::
			- Quotes
			- Liked
			- Summary
			- Permanent notes
- This template captures everything I might need for a movie
	- Movie
	  template:: Movie
	  template-including-parent:: false
		- title:: 
		  imdb::
		  status:: 
		  type:: #movie
		  year::
		  topics::
		  genre::
		  tags::
		  icon:: 🎥
		  recommendedBy::
		  watched::
		  rating:: ⭐️
		  digested::
			- Quotes
			- Liked
			- Summary
			- Permanent notes
- This template captures everything I might need for a song
	- Song
	  template:: Song
	  template-including-parent:: false
		- title:: 
		  artist::
		  type:: #song
		  url:: 
		  year::
		  genre::
		  tags::
		  icon:: 🎵
		  rating:: ⭐️
		  Details::
			- Chords
			- Lyrics
			- Notes
- This template suggests filling in some properties for a Todo
	- TODO -
	  template:: MyTodo
	  template-including-parent:: falseTODO -
	  created:: <%today%>
	  scheduled:: <%tomorrow%>
	  deadline:: <%tomorrow%>
	  done::
	  tags::
	  details:
		- First Detail
- This is a template for my daily journal to try to force work on the things I want to work on.  I'm starting with the keyword `#habit` in the hopes that I can eventually look into using [Logseq Habit Tracker](https://github.com/c6p/logseq-habit-tracker)
	- #habit
	  template:: Daily Habits
	  template-including-parent:: true
		- #Exercise
		- #Housework
		- #Coding
		- #Music
		- #Social/Networking
	-
	-
	-
- My goal is to use this page for all templates, but this query should find any other stragglers:
	- This query did NOT Filter out templates from this page: ``{{query (and (property template) (not (property title Templates))) }}``
	- This query shows templates defined anywhere else in the graph:
	  #+BEGIN_QUERY
	  {
	   :query [:find (pull ?b [*])
	           :where
	           [?b :block/properties ?prop]
	           [(get ?prop :template) ?t]
	           (not [?b :block/page [:block/name "templates"]] )
	      ]
	      :collapsed? true
	  }
	  #+END_QUERY
- Here are some resources to check out when working with templates:
	- [logseq templates documentation](https://docs.logseq.com/#/page/templates)
	- [How to Set Up an Automated Daily Template in Logseq](https://thinkstack.club/how-to-set-up-an-automated-daily-template-in-logseq/)
	- [Dario's github of templates](https://github.com/dario-ds/logseq/blob/main/templates.md)
-