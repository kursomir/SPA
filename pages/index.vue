<template lang="pug">
  div
    - var subtopics = ["Физика", "Химия", "Математика", "История искусства", "Музыка"];
    - var specialty = ["Теория музыки", "История музыки", "Исполнение музыки"];

    .head-cover(:style="{ 'background-image': `url(${curiosityImg})` }")
    .document-content
      .content-head
        .wrapper
          h1.title Курсы
          select.select-box(name="subtopic")
            option(value="" selected) Предмет
            for stopic in subtopics
              option
                = stopic
          select.select-box(name="specialty")
            option(value="" selected) Направление
            for spec in specialty
              option
                = spec
          form.search-box
            input.input(type="text" placeholder="Поиск")
            button.submit(type="submit")
              svg.svg-icon.-loupe(role="img" title="loupe")
                use(xlink:href="icons.svg#icon-loupe")
      .content-body
        .wrapper
          .sort-tools
            .grid-type
              .item.-active
                svg.svg-icon.-card_view(role="img" title="card_view")
                  use(xlink:href="icons.svg#icon-card_view")
              .item
                svg.svg-icon.-list_view(role="img" title="list_view")
                  use(xlink:href="icons.svg#icon-list_view")
            .sort-tools-sortby
              span.label Сортировать по:
              select.select
                option Названию
                option Дате добавления
                option Имени лектора
            .sort-tools-contains
              .field
                input.checkbox(type="checkbox" id="contains")
                label(for="contains")
                  svg.svg-icon.-check(role="img" title="loupe")
                    use(xlink:href="icons.svg#icon-check")
                  | Содержит видео/аудио
          //- Курсы в виде списка
          //- .content-body-main
            .list-box
              .list.-unmargin-top
                - for (var i=0; i<=10; i++)
                  if i == 0
                    li.course-item.-unborder-top
                      a.title(href="javascript:;") Mechanics of Material Systems
                      a.teacher(href="javascript:;") Кевин Колтер
                  else
                    li.course-item
                      a.title(href="javascript:;") Mechanics of Material Systems
                      a.teacher(href="javascript:;") Кевин Колтер
              .showmore
                a.button-box.-medium(href="javascript:;") Показать еще 30
          //- Курсы в виде карточек
          .list-box.-card
            .list
              - for (var i=0; i<=10; i++)
                li.course-item.-card
                  a.image(href="javascript:;")
                    img(src="~assets/images/cover.jpg")
                  .info
                    a.teacher(href="javascript:;") Кевин Колтер
                    a.title(href="javascript:;") Mechanics of Material Systems
            .showmore
              a.button-box.-medium(href="javascript:;") Показать еще 30
</template>

<script>
  import curiosityImg from 'assets/images/curiosity.png'

  export default {
    data () {
      return {
        curiosityImg
      }
    }
  }
</script>
