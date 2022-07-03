cache_handler - File cache handler for Hollywood with optional compression and max size limit

Hollywood is a commercial multimedia-oriented programming language that can be used to create applications and games very easily (https://hollywood-mal.com/)

This scripts needs sqlite3 Hollywood plugin (https://hollywood-mal.com/download.html) and exposes several functions to Hollywood scripts :
- cache_handler.Add(key$, content$) : add content$ associated to key key$. If a content is already associated to key$ it is overwritten
- cache_handler.Remove(key$) : remove the content associated with key$
- cache_handler.Contains(key$) : returns True if there is a content associated with keys, False otherwise
- cache_handler.Get(key$) : returns the content associated with key$ or Nil if nothing is associated with key$
- cache_handler.Clear() : clear the cache by removing all key/content
- cache_handler.ActivateCompression(activation) : if activation is True future content will be compressed before being inserted. Contents are compressed using zlib
- cache_handler.MaximumSize(size) : if size > 0 then older contents are removed before inserting new ones to try to not go beyond size. By default there is no limit to the size of the cache
- cache_handler.CurrentSize() : return the total size (in bytes) of the cache
