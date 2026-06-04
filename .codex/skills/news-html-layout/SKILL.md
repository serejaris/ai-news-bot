---
name: news-html-layout
description: |
  Использовать, когда нужно сверстать готовый русскоязычный текст новости в отдельную HTML-страницу для статического блога.
  Скилл требует Tailwind CDN, SEO/meta/social tags, article schema и не допускает кастомные CSS-файлы или style-блоки.
---

# Верстка HTML-новости

Этот скилл превращает готовый текст новости в отдельную HTML-страницу для статического блога.

## Когда использовать

Использовать, когда есть готовый текст новости и нужно:

- сделать отдельную HTML-страницу;
- подготовить страницу для GitHub Pages;
- добавить SEO-теги;
- добавить Open Graph и Twitter meta;
- оформить текст через Tailwind CDN;
- сохранить страницу в `news/<slug>-YYYY-MM-DD.html`.

## Вход

Нужны:

- заголовок;
- дата публикации;
- лид;
- основной текст;
- slug латиницей;
- краткое SEO-описание;
- абсолютный URL будущей страницы;
- URL картинки для social preview, если она есть.

## Жесткие правила

- Не писать CSS-файлы.
- Не добавлять `<style>`.
- Не использовать inline `style`.
- Использовать только Tailwind CDN: `<script src="https://cdn.tailwindcss.com"></script>`.
- Каждая новость должна быть отдельной HTML-страницей.
- Ссылки на главную должны работать и локально, и на GitHub Pages.
- Текст должен быть читаемым на мобильном и десктопе.

## Обязательные SEO-теги

В каждой странице должны быть:

- `<title>`;
- `<meta name="description">`;
- `<meta name="robots" content="index, follow">`;
- `<link rel="canonical">`;
- `og:type`;
- `og:site_name`;
- `og:title`;
- `og:description`;
- `og:url`;
- `og:image`, если есть картинка;
- `twitter:card`;
- `twitter:title`;
- `twitter:description`;
- `twitter:image`, если есть картинка;
- `article:published_time` для новостей.

## Структура страницы

Использовать такую структуру:

1. `<!doctype html>` и `<html lang="ru">`.
2. `<head>` с SEO/social/schema meta.
3. Tailwind CDN.
4. Header с названием блога и ссылкой на главную.
5. `<main>` с `<article>`.
6. Категория и дата.
7. H1.
8. Лид.
9. Секции статьи с H2.
10. Финальный блок `Что это значит для читателя`, если он есть в тексте.

## JSON-LD

Добавлять `NewsArticle`:

- `headline`;
- `datePublished`;
- `dateModified`;
- `author`;
- `publisher`;
- `inLanguage: ru`.

## Проверка

Перед отдачей проверить:

- нет `<style>` и `style=`;
- есть Tailwind CDN;
- есть canonical URL;
- есть Open Graph и Twitter tags;
- есть H1;
- страница открывается по локальному URL;
- ссылка на главную работает.
