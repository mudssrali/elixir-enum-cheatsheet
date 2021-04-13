# Elixir Enum Cheatsheet
a simple elixir enum cheatsheet

## Functions

- `all?`
    ```ex
    
    [👋🏼,🤚🏼,🖐🏼,✋🏼,🖖🏼,👌🏼] |> Enum.all?( fn x -> x == 👌🏼 end)// false

    ```

- `any?`
    ```ex
    
   [👋🏼,🤚🏼,🖐🏼,✋🏼,🖖🏼,👌🏼] |> Enum.all?( fn x -> x == 👌🏼 end)// true

    ```

- `at`
    ```ex
    
    [😀,😃,😄,😁,😆,😅] |> Enum.at(5)// 😅

    ```


- `chunk_by`
    ```ex
    
     [😀,😃,😁,😆,😅] |> Enum.chunk_by(fn x -> x == 😁)// [[😀,😃],[😁], [😆,😅]]

    ```

- `chunk_every`
    ```ex
    
    [👏,🙌,👐,🤲,🤝] |> Enum.chunk_every(2)// [[👏,🙌],[👐,🤲],[🤝]]

    ```

- `chunk_while`
    ```ex
    
    [] |> Enum.chunk_while()

    ```

- `concat`
    ```ex
    
    [] |> Enum.concat()

    ```

- `count`
    ```ex
    
    [] |> Enum.count()

    ```

- `dedup`
    ```ex
    
    [] |> Enum.dedup()

    ```

- `dedup_by`
    ```ex
    
    [] |> Enum.dedup_by()

    ```

- `drop`
    ```ex
    
    [] |> Enum.drop()

    ```

- `drop_every`
    ```ex
    
    [] |> Enum.drop_every()

    ```

- `drop_while`
    ```ex
    
    [] |> Enum.drop_while()

    ```

- `each`
    ```ex
    
    [] |> Enum.each()

    ```

- `empty?`
    ```ex
    
    [] |> Enum.empty?()

    ```

- `fetch`
    ```ex
    
    [] |> Enum.fetch()

    ```

- `filter`
    ```ex
    
    [] |> Enum.filter()

    ```

- `find`
    ```ex
    
    [] |> Enum.find()

    ```

- `find_index`
    ```ex
    
    [] |> Enum.find_index()

    ```

- `find_value`
    ```ex
    
    [] |> Enum.value()

    ```

- `flat_map`
    ```ex
    
    [] |> Enum.map()

    ```

- `flat_map_reduce`
    ```ex
    
    [] |> Enum.flat_map_reduce()

    ```

- `frequencies`
    ```ex
    
    [] |> Enum.frequencies()

    ```

- `frequencies_by`
    ```ex
    
    [] |> Enum.frequencies_by()

    ```

- `group_by`
    ```ex
    
    [] |> Enum.group_by()

    ```

- `intersperse`
    ```ex
    
    [] |> Enum.intersperse()

    ```

- `into`
    ```ex
    
    [] |> Enum.into()

    ```

- `join`
    ```ex
    
    [] |> Enum.join()

    ```

- `map`
    ```ex
    
    [] |> Enum.map()

    ```

- `map_every`
    ```ex
    
    [] |> Enum.map_every()

    ```

- `map_intersperse`
    ```ex
    
    [] |> Enum.map_intersperse()

    ```

- `map_join`
    ```ex
    
    [] |> Enum.map_join()

    ```

- `map_reduce`
    ```ex
    
    [] |> Enum.map_reduce()

    ```

- `max`
    ```ex
    
    [] |> Enum.max()

    ```

- `max_by`
    ```ex
    
    [] |> Enum.max_by()

    ```

- `member?`
    ```ex
    
    [] |> Enum.member?()

    ```

- `min`
    ```ex
    
    [] |> Enum.min()

    ```
- `min_by`
    ```ex
    
    [] |> Enum.min_by()

    ```

- `min_max`
    ```ex
    
    [] |> Enum.min_max()

    ```

- `min_max_by`
    ```ex
    
    [] |> Enum.min_max_by()

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