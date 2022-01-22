# Elixir Enum Cheatsheet

a simple elixir enum cheatsheet

## Functions

- `all?`

  ```ex

  [👋🏼 🤚🏼 🖐🏼 ✋🏼 🖖🏼 👌🏼] |> Enum.all?( fn x -> x == 👌🏼 end) ---> false

  ```

- `any?`

  ```ex

  [👋🏼 🤚🏼 🖐🏼 ✋🏼 🖖🏼 👌🏼] |> Enum.any?( fn x -> x == 👌🏼 end) ---> true

  ```

- `at`

  ```ex

  [😀 😃 😄 😁 😆 😅] |> Enum.at(5) ---> 😅

  ```

- `chunk_by`

  ```ex

   [😀 😃 😁 😆 😅] |> Enum.chunk_by(fn x -> x == 😁) ---> [[😀 😃] [😁]  [😆 😅]]

  ```

- `chunk_every`

  ```ex

  [👏 🙌 👐 🤲 🤝] |> Enum.chunk_every(2) ---> [[👏 🙌] [👐 🤲] [🤝]]

  ```

- `concat`

  ```ex

  [🐶 🐱 🐭] |> Enum.concat([🐹 🐰 🦊]) ---> [🐶 🐱 🐭 🐹 🐰 🦊]

  ```

- `count`

  ```ex

  [🐶 🐱 🐭 🐹 🐰 🦊] |> Enum.count() ---> 6

  ```

- `dedup` - remove consecutive duplicates

  ```ex

  [🐹 🐰 🦊 🦊 🐹 🐰] |> Enum.dedup() ---> [🐹 🐰 🦊 🐹 🐰]

  ```

- `drop`

  ```ex

  [👋🏼 🤚🏼 🖐🏼 🦊 🐹 🐰] |> Enum.drop(3) ---> [🦊 🐹 🐰]

  ```

- `drop_every`

  ```ex

  1..10 |> Enum.drop_every(2) ---> [2, 4, 6, 8, 10]
  1..10 |> Enum.drop_every(1) ---> []
  1..10 |> Enum.drop_every(0) ---> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

  ```

- `drop_while`

  ```ex

  1..10 |> Enum.drop_while(fn x -> x < 5 end) ---> [6, 7, 8, 9, 10]

  ```

- `each`

  ```ex

  1..2 |> Enum.each(fn x -> IO.puts(x) end) ---> 1 \n 2

  ```

- `empty?`

  ```ex

  [] |> Enum.empty?() ---> true

  ```

- `fetch`

  ```ex

  [👋🏼 🤚🏼 🖐🏼 🦊 🐹 🐰] |> Enum.fetch(3) ---> {:ok, 🦊}

  ```

- `filter`

  ```ex

  1..10 |> Enum.filter(fn x -> rem(x, 2) == 0 end) --> [2, 4, 6, 8, 10]

  ```

- `find`

  ```ex

   [🐹 🐰 🦊 🦊 🐹 🐰] |> Enum.find(fn x -> x == 🦊 end) ---> 🦊

  ```

- `find_index`

  ```ex

   [🐹 🐰 🦊 🦊 🐹 🐰] |> Enum.find(fn x -> x == 🦊 end) ---> 2

  ```

- `flat_map`

  ```ex

  ["🐹", "🦊"] |> Enum.flat_map(fn x -> [x, x] end) ---> [["🐹", "🐹"], ["🦊", "🦊"]]

  ```

<!-- - `flat_map_reduce`
    ```ex

    [] |> Enum.flat_map_reduce()

    ``` -->

- `frequencies`

  ```ex

  ["🐹", "🐰", "🦊", "🦊", "🐹"] |> Enum.frequencies() ---> %{"🐰" => 1, "🐹" => 2, "🦊" => 2}

  ```

- `frequencies_by`

  ```ex
  ["🐹", "🐰", "🦊", "🦊", "🐹"] |> Enum.frequencies_by(fn x -> x == "🦊" end) ---> %{false: 3, true: 2}

  ```

- `group_by`

  ```ex
   ["🐹", "🐰", "🦊", "🦊", "🐹"] |> Enum.group_by(fn x -> x end) ---> %{"🐹" => ["🐹","🐹"], "🐰" => ["🐰"], "🦊" => ["🦊","🦊"]}
  ```

  ```ex
   ["🐹", "🐰", "🦊", "🦊", "🐹"] |> Enum.group_by(fn x -> x end, fn x -> nameOf(x) end)
   ---> %{"🐹" => ["bear","bear"], "🐰" => ["rabbit"], "🦊" => ["fox","fox"]}

  ```

- `intersperse`

  ```ex

  ["🐹", "🦊", "🦊", "🐹"] |> Enum.intersperse("🐰") --->  ["🐹", "🐰", "🦊", "🐰", "🦊", "🐰", "🐹"]

  ["🐹"] |> Enum.intersperse("🐰") --->  ["🐹"]

  [] |> Enum.intersperse("🐰") --->  []

  ```

- `into`

  ```ex

   ["🐹", "🦊", "🦊", "🐹"] |> Enum.into([]) --->  ["🐹", "🦊", "🦊", "🐹"]

   %{bear: "🐹", fox: "🦊"} |> Enum.into([]) ---> [bear: "🐹", fox: "🦊"]

   %{bear: "🐰", fox: "🦊", bear: "🐹"} |> Enum.into([]) ---> [bear: "🐹", fox: "🦊"]

  ```

  ```ex

   ["🐹", "🦊", "🦊", "🐹"] |> Enum.into([], fn x -> nameOf(x) end) --->  ["bear", "fox", "fox", "bear"]

  ```

- `join`

  ```ex

   ["🐹", "🦊", "🦊", "🐹"] |> Enum.join("🐰") ---> "🐹🐰🦊🐰🦊🐰🐹"

  ```

- `map`

  ```ex

  ["🐹", "🦊", "🦊", "🐹"] |> Enum.map(fn x -> "#{x}🐰" end) ---> ["🐹🐰", "🦊🐰", "🦊🐰", "🐹🐰"]

  ```

- `map_every`

  ```ex

  ["🐹", "🦊", "🦊", "🐹"] |> Enum.map_every(2, fn x -> "#{x}🐰" end) ---> ["🐹", "🦊🐰", "🦊", "🐹🐰"]

  ```

- `map_intersperse`

  ```ex

   ["🐹", "🦊", "🦊", "🐹"] |> Enum.map_intersperse("🐶", fn x -> "#{x}🐰" end) ---> ["🐹🐰", "🐶🐰", "🦊🐰", "🐶🐰", "🦊🐰", "🐶🐰", "🐹🐰"]

  ```

- `map_join`

  ```ex

   ["🐹", "🦊", "🦊", "🐹"] |> Enum.map_join("🐶", fn x -> "#{x}🐰" end) ---> "🐹🐰🐶🦊🐰🐶🦊🐰🐶🐹🐰"


  ```

- `map_reduce`

  ```ex

  ["🐹", "🦊", "🦊", "🐰"] |> Enum.map_reduce("🐶", fn x, acc -> {"#{x}🐰", "#{x}#{acc}"} end) ---> {["🐹🐰", "🦊🐰", "🦊🐰", "🐰🐰"], "🐰🦊🦊🐹🐶" }

  ```

- `max`

  ```ex

  [1, 3, 6, 9] |> Enum.max() ---> 9

  ```

- `max_by`

  ```ex

  ["🐹", "🦊", "🦊", "🐰"] |> Enum.max_by(fn x -> nameOf(x) end) ---> "🐰"

  ```

- `member?`

  ```ex

   ["🐹", "🦊", "🦊", "🐰"] |> Enum.member?("🐰") ---> true


   ["🐹", "🦊", "🦊" |> Enum.member?("🐰") ---> false

  ```

- `min`

  ```ex

  [1, 3, 6, 9] |> Enum.min() ---> 1

  ```

- `min_by`

  ```ex

  ["🐹", "🦊", "🦊", "🐰"] |> Enum.min_by(fn x -> nameOf(x) end) ---> "🐹"

  ```

- `min_max`

  ```ex

  [1, 2, 3, 4, 5, 9] |> Enum.min_max() ---> {1, 9}

  ```

- `min_max_by`

  ```ex

  ["🐹", "🦊", "🦊", "🐰"] |> Enum.min_max_by(fn x -> nameOf(x) end) ---> {"🐹", "🐰"}

  ```

- `random`

  ```ex

  [] |> Enum.random()

  ```

- `reduce`

  ```ex

  [] |> Enum.reduce()

  ```

- `reduce_while`

  ```ex

  [] |> Enum.reduce_while()

  ```

- `reject`

  ```ex

  [] |> Enum.reject()

  ```

- `reverse`

  ```ex

  [] |> Enum.reverse()

  ```

- `reverse_slice`

  ```ex

  [] |> Enum.reverse_slice()

  ```

- `scan`

  ```ex

  [] |> Enum.scan()

  ```

- `shuffle`

  ```ex

  [] |> Enum.shuffle()

  ```

- `slice`

  ```ex

  [] |> Enum.slice()

  ```

- `sort`

  ```ex

  [] |> Enum.sort()

  ```

- `sort_by`

  ```ex

  [] |> Enum.sort_by()

  ```

- `split`

  ```ex

  [] |> Enum.split()

  ```

- `split_while`

  ```ex

  [] |> Enum.split_while()

  ```

- `split_with`

  ```ex

  [] |> Enum.split_with()

  ```

- `sum`

  ```ex

  [] |> Enum.sum()

  ```

- `take`

  ```ex

  [] |> Enum.take()

  ```

- `take_every`

  ```ex

  [] |> Enum.take_every()

  ```

- `take_random`

  ```ex

  [] |> Enum.take_random()

  ```

- `take_while`

  ```ex

  [] |> Enum.take_while()

  ```

- `to_list`

  ```ex

  [] |> Enum.to_list()

  ```

- `uniq`

  ```ex

  [] |> Enum.uniq()

  ```

- `uniq_by`

  ```ex

  [] |> Enum.uniq_by()

  ```

- `unzip`

  ```ex

  [] |> Enum.unzip()

  ```

- `with_index`

  ```ex

  [] |> Enum.with_index()

  ```

- `zip`

  ```ex

  [] |> Enum.zip()

  ```
