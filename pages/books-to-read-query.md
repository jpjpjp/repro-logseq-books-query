id:: 62f64752-3685-4684-8c8a-d27929ee22d2
  #+BEGIN_QUERY
  {:title [:h2 "What to read next"]
   :query [:find (pull ?b [*])
           :where
  		[has-property ?b :type]
          [property ?b :type "book"]
          [property ?b :status "toread"]
  ]}
  #+END_QUERY
