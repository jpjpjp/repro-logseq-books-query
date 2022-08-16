query-table:: false
id:: 62f67099-316d-4cc3-8f74-c8a334d5fa84
  #+BEGIN_QUERY
  {:title [:h4 "Finished"]
   :query [:find (pull ?b [*])
           :where
  		[has-property ?b :type]
          [property ?b :type "book"]
          [property ?b :status "read"]
  ]}
  #+END_QUERY

-
-
-