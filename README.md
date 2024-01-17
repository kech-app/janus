# Janus - A UX DSL

*"Light is a wave, no Light is a particle"*


![image](https://github.com/kech-app/janus/assets/4276047/dc489bb7-d653-43d6-964e-a19530246c7a)

## Introduction

- Data Modellers make data schemas
- Interaction Designers make graphical interfaces
- LLMs and Programmers write code

This project is a [Janusian Thinking](https://www.creativitypost.com/article/janusian_thinking) design effort to revisit how we think about UI for software applications.

We are respecting contradictory perspectives to the application design effort: 
- **dividing**-analyzing - conquer & conquest - **loved** by engineers - pragmatism - working **things**
- **unifying**-synthesizing - unified perspective - **loved** by designers - harmony - beautiful **things**

Using Janus should be very simple, but Designing it can be hard.

So we will start with the simple: The Janus DSL user perspective.

## Janus basics: Attributes, Widgets and Fields

in Janus:

$$field = attribute + widget$$

let sketch some code :

```elixir
defmodule Demo.Tickets.Representative do
  use Ash.Resource,
  extensions: [
    Kech.Janus.Resource
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
widgets do
  wigdet :text_widget do
    heex: :tailwind, "<input class='px4 mx5 text-xl' value="@value" /><input>  # this is easy to design
    heex: :carbonui_wc, "<cds-text-imput ...></cds-text-imput> # this is easy to design
    volt: :tailwind       # NB: I don't understand VOLT yet, but I have to consider it, for the love of ash
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

## ViewArchitectures DSL
coming soon

## Archetypes DSL
coming soon

## UX Grammar DSL
NOT coming soon

## UX Flow DSL
NOT coming soon

# Disclaimer
I am not inventing any new concept. I am just curating good designs and putting a DSL together.

