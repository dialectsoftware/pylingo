## pylingo

General purpose extensible configuration language.

```bash

config {
  {key} = { object | array | scalar }
}

import "{name}" {
  version = "0.0.0"
  module  = "{scalar}"
}

variable "{name}" {
	{key} = { object | array | scalar }
}

data "{source}" "{name}" {
    {key} = { object | array | scalar }
}


generator "{type}" "{name}" {
  {key} = { object | array | scalar }
}



