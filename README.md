# BindHtml

Bind data to HTML views.

## Usage

```elixir
import BindHtml
view = """
<div data-scope="post">
  <p data-prop="body">Example content.</p>
  <ul>
    <li data-prop="authors">Author</li>
  </ul>
</div>
"""
data = [
  %{"id" => 1, "body" => "First!", "authors" => ["Jay", "Les"]},
  %{"id" => 2, "body" => "Second!", "authors" => ["Sue", "Joe"]},
]

bind(view, data, :post)
# =>
# <div data-scope="post" data-id="1">
#   <p data-prop="body">First!</p>
#   <ul>
#     <li data-prop="authors">Jay</li>
#     <li data-prop="authors">Les</li>
#   </ul>
# </div>
# <div data-scope="post" data-id="2">
#   <p data-prop="body">Second!</p>
#   <ul>
#     <li data-prop="authors">Sue</li>
#     <li data-prop="authors">Joe</li>
#   </ul>
# </div>
```
