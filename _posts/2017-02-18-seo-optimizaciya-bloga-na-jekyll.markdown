---
layout: post
title: SEO оптимизация блога на Jekyll
description: Обзор SEO плагинов которые я использую для оптимизации блога на Jekyll и GitHub Pages.
date: 2017-02-18 16:43:45 +0200
---

Я выполнил первую задачу из [списка целей](http://artego.space/moi-celi), которая касалась блога. Еще один маленький шаг сделан. И так по порядку.

## jekyll-seo-tag плагин

Мощный [плагин jekyll-seo-tag](https://github.com/jekyll/jekyll-seo-tag) предназначен для работы с мета тегами, которые используют поисковые системы. Также плагин позволяет настроить теги, которые используют различные социальные сети для интеграции вашего контента при репостах. Настраивается плагин следующим образом:

Добавить следующую строку в `Gemfile`:

  ```ruby
  gem 'jekyll-seo-tag'
  ```

Добавить запись в файл `_config.yml`:

  ```yml
  gems:
    - jekyll-seo-tag
  ```

Добавить [liquid tag](https://shopify.github.io/liquid/basics/introduction/#tags) {% raw %}`{% seo %}`{% endraw%} перед тегом `</head>` в шаблон темы вашего сайта:

  ```liquid
  <head>
      …
      {% raw %}{% seo %}{% endraw%}
  </head>
  ```
Теперь все должно работать. Не забудьте перезапустить сервер, если вы ведете разработку на локальной машине и проверьте, работает ли установленный плагин. Для этого откройте любую страницу вашего сайта и просмотрите ее исходный код. Убедитесь, что теги, выводимые плагином не дублируют те, которые выводит ваша тема.

После установки плагина, следует определиться с тегами, которые вы желаете отображать. В каждый пост, во [front matter](https://jekyllrb.com/docs/frontmatter/), я добавил тег `description`. Этот тег Google использует как краткое описание страницы в результатах поисковой выдачи. Нет стопроцентной гарантии того, что Google будет использовать текст тега для отображения описания. Он может посчитать более релевантной другую часть текста на странице.

Желательно составлять такое описание, которое будет максимально точно характеризовать содержимое вашей страницы. Длина описания должна составлять 150 - 160 символов.

Плагин jekyll-seo-tag удовлетворит требование даже самого изощренного SEO специалиста, однако я решил ограничится базовым набором необходимых тегов.

## jekyll-sitemap плагин

[Плагин jekyll-sitemap](https://github.com/jekyll/jekyll-sitemap/) автоматически генерирует файл `sitemap.xml`, который используют поисковики для получения информации о том, какие страницы сайта им нужно проиндексировать и как часто обновляется контент на конкретной странице.

## Страница 404

Благо для того, чтобы создать кастомную страницу 404 не нужно никаких плагинов. Необходимо создать файл `404.md` или `404.html` в корне проэкта. Код моей страницы пока выглядит так:

```markdown
---
layout: default
title: Страница не найдена
sitemap: false
---

Страница не найдена =(

Возможно она была удалена или неправильно указан адрес страницы.

```

Я провел лишь базовую оптимизацию блога  и остальные работы буду проводить по мере необходимости. А на данный момент есть более [важные цели](http://artego.space/moi-celi), которые требуют моего внимания.

Обязательно поделитесь в комментариях своими мыслями и опытом оптимизации блогов.

