id:: 62f64752-6d6a-49e2-9fe9-2a64e02af28f
#+BEGIN_QUERY
{:title [:h3 "Currently Reading"]
 :query [:find (pull ?b [*])
         :where
        [property ?b :type "book"]
        [property ?b :status "reading"]
]}
#+END_QUERY
