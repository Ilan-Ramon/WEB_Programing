# שיעור 6 — אבני הבניין: div, class, button ו-Grid

קובץ פתיחה לתרגול על `<div>`, `class`, `<button>` ו-CSS Grid.

## איך מתחילים
1. פתחו את `blocks.html` בדפדפן.
2. פתחו את שני הקבצים בעורך הקוד.
3. הוסיפו עוד כרטיסים לרשת — כל כרטיס הוא `div` חדש עם `class="card"`.
4. נסו לשנות את מספר העמודות ב-`grid-template-columns`.


## הסבר על תוכן קובץ ה-CSS

### `*` — בורר כללי

```css
* { box-sizing: border-box; }
```

בורר כללי שחל על כל אלמנט בעמוד. `box-sizing: border-box` גורם לכך שכשמגדירים רוחב/גובה לאלמנט, ה-padding וה-border נכללים בתוך המידה הזו (ולא מתווספים עליה). זה מונע הפתעות בגדלים כשיש padding.

### `body`

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    margin: 0;
    padding: 24px;
}
```

מעצב את גוף הדף כולו: פונט Arial (עם sans-serif כגיבוי), רקע אפור בהיר, מבטל את המרווח הדיפולטיבי שהדפדפן מוסיף סביב הדף (`margin: 0`), ומוסיף ריפוד של 24 פיקסלים סביב התוכן.

### `.grid`

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
}
```

כל אלמנט עם class בשם "grid" הופך ל-CSS Grid — פריסה שמסדרת ילדים בשורות ועמודות. כאן זה מגדיר 3 עמודות שוות רוחב (`repeat(3, 1fr)` = חזור 3 פעמים על עמודה ברוחב יחסי 1), עם רווח של 16 פיקסלים בין הפריטים. זה בדיוק מה שההערה בסוף קובץ ה-CSS מרמזת שכדאי לנסות לשנות.

### `.card`

```css
.card {
    background-color: white;
    border: 1px solid #dddddd;
    border-radius: 8px;
    padding: 16px;
    text-align: center;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}
```

מעצב כל אלמנט עם class "card" — כנראה כרטיסיות בתוך ה-grid. רקע לבן, מסגרת אפורה דקה, פינות מעוגלות (8px), ריפוד פנימי, טקסט ממורכז, וצל עדין מתחת לכרטיסיה שנותן תחושת עומק.

### `.card h2`

```css
.card h2 {
    margin-top: 0;
    color: #1f497d;
}
```

זה בורר "מקונן" — חל רק על תגיות `<h2>` שנמצאות בתוך אלמנט עם class "card". מבטל את המרווח העליון הדיפולטיבי של כותרת h2 (כדי שלא תיצור רווח מיותר בראש הכרטיסיה) וצובע אותה בכחול כהה.

### `button`

```css
button {
    background-color: #f79646;
    color: white;
    border: none;
    border-radius: 6px;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
}
```

מעצב את כל כפתורי ה-`<button>` בעמוד: רקע כתום, טקסט לבן, ללא מסגרת, פינות מעוגלות, ריפוד (10px למעלה/למטה, 20px לצדדים), גודל פונט 16px, וסמן עכבר שהופך ל"יד" (`cursor: pointer`) כדי לרמז שאפשר ללחוץ.

### `button:hover`

```css
button:hover {
    background-color: #e07f2a;
}
```

פסאדו-קלאס (pseudo-class) — מגדיר איך הכפתור נראה כשהעכבר מרחף מעליו: הרקע הופך לכתום כהה יותר, נותן פידבק ויזואלי שהכפתור אינטראקטיבי.