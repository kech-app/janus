# LUX - A UX DSL

*"Light is a wave, no Light is a particle"*

## Introduction

- Data Modellers make data schemas
- Interaction Designers make graphical interfaces
- LLMs and Programmers write code

LUX is a [Janusian Thinking](https://www.creativitypost.com/article/janusian_thinking) design effort to revisit how we think about UI for software applications.

Using LUX should be very simple, but Designing LUX can be hard.

So we will start with the simple: The LUX DSL user perspective.

## Previous art
Who cares about previous art, anyway?

You can Google it or ask GPT if you care.

## Lux basics: Attributes, Widgets and Fields

in LUX:

$$field = attribute + widget$$

let sketch some code :

```elixir
defmodule Demo.Tickets.Representative do
  use Ash.Resource,
  extensions: [
    Kech.Lux.Resource
  ]

  attributes do
    uuid_primary_key :id

    attribute :first_name, :string
    attribute :last_name, :string
    attribute :representative, :boolean
    attribute :resume, :string
  end

  fields do
      field :first_name, :text_widget 
      field :last_name, :text_widget
      field :representative, :checkbox_widget
      field :resume, :markdown_editor
      field :full_name, :text_widget # this is not an attribute, it's maybe calculation
  end
```

somewhere else we define widgets:
```elixir
widgets
  wigdet :text_widget do
    heex: :tailwind, "<input class='px4 mx5 text-xl' value="@value" /><input>  # this is easy to design
    heex: :carbonui_wc, "<cds-text-imput ...></cds-text-imput> # this is easy to design
    jsx:  :carbon_react   # Hey Chakib, this is Hard to design, and you promised we stay simple ! lol
  end  
  
  wigdet :markdown_widget do
    heex:
    heex:
    ...
  end  
end
```

## Views DSL 
coming soon
..
## ViewArchitectures DSL
coming soon
..
## Archetypes DSL
coming soon
..

# UX Magic Grammar DSL
not coming soon. 
..

# UX Magic Flow DSL
not coming soon
..

