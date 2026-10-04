# TESTVC
# <!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Бюджет нейрокреатора</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

:root {
    --bg: #f5f6fa;
    --card: #ffffff;
    --text: #18181b;
    --muted: #71717a;
    --border: #e4e4e7;

    --purple: #7c3aed;
    --purple-light: #f3e8ff;

    --green: #16a34a;
    --green-light: #dcfce7;

    --red: #dc2626;
    --red-light: #fee2e2;

    --blue: #2563eb;
    --blue-light: #dbeafe;

    --orange: #ea580c;
    --orange-light: #ffedd5;

    --radius: 18px;
    --shadow: 0 8px 25px rgba(0,0,0,0.06);
}

body {
    font-family: Arial, sans-serif;
    background: var(--bg);
    color: var(--text);
    padding: 30px 16px 60px;
}

button,
input {
    font: inherit;
}

.container {
    max-width: 1150px;
    margin: auto;
}

/* =========================
   ШАПКА
========================= */

.header {
    margin-bottom: 28px;
}

.badge {
    display: inline-block;
    background: var(--purple-light);
    color: var(--purple);
    padding: 7px 12px;
    border-radius: 100px;
    font-size: 13px;
    font-weight: bold;
    margin-bottom: 12px;
}

.header h1 {
    font-size: clamp(28px, 5vw, 44px);
    margin-bottom: 10px;
}

.header p {
    color: var(--muted);
    line-height: 1.6;
    max-width: 700px;
}


/* =========================
   ГЛАВНЫЕ ПОКАЗАТЕЛИ
========================= */

.summary {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin-bottom: 25px;
}

.summary-card {
    background: white;
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 22px;
    box-shadow: var(--shadow);
}

.summary-label {
    color: var(--muted);
    font-size: 14px;
    margin-bottom: 10px;
}

.summary-value {
    font-size: 28px;
    font-weight: 800;
}

.income-value {
    color: var(--green);
}

.expense-value {
    color: var(--red);
}

.profit-value {
    color: var(--purple);
}


/* =========================
   СЕКЦИИ
========================= */

.grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}

.section {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 22px;
    box-shadow: var(--shadow);
}

.section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 18px;
}

.icon {
    width: 44px;
    height: 44px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 21px;
}

.income-section .icon {
    background: var(--green-light);
}

.ai-section .icon {
    background: var(--purple-light);
}

.social-section .icon {
    background: var(--blue-light);
}

.internet-section .icon {
    background: var(--orange-light);
}

.section h2 {
    font-size: 19px;
}

.description {
    color: var(--muted);
    font-size: 12px;
    margin-top: 3px;
}


/* =========================
   СТРОКИ
========================= */

.budget-row {
    display: grid;
    grid-template-columns: minmax(0,1fr) 145px 40px;
    gap: 8px;
    margin-bottom: 10px;
}

.budget-row input {
    width: 100%;
    border: 1px solid var(--border);
    background: #fafafa;
    border-radius: 10px;
    padding: 11px;
    outline: none;
}

.budget-row input:focus {
    background: white;
    border-color: var(--purple);
    box-shadow: 0 0 0 3px rgba(124,58,237,0.08);
}

.amount {
    text-align: right;
}

.delete {
    border: none;
    border-radius: 10px;
    background: var(--red-light);
    color: var(--red);
    font-size: 18px;
    cursor: pointer;
}

.add {
    width: 100%;
    margin-top: 5px;
    padding: 11px;
    border: 1px dashed #c4b5fd;
    border-radius: 10px;
    background: #faf5ff;
    color: var(--purple);
    font-weight: bold;
    cursor: pointer;
}

.add:hover {
    background: var(--purple-light);
}

.section-total {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    border-top: 1px solid var(--border);
    padding-top: 16px;
    margin-top: 17px;
    font-weight: bold;
}

.section-total strong {
    font-size: 19px;
}


/* =========================
   ГЛАВНЫЙ РЕЗУЛЬТАТ
========================= */

.result {
    margin-top: 24px;
    background: #18181b;
    color: white;
    border-radius: 22px;
    padding: 28px;
}

.result-title {
    font-size: 22px;
    margin-bottom: 20px;
}

.result-line {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    padding: 11px 0;
    border-bottom: 1px solid rgba(255,255,255,0.1);
}

.result-line span {
    color: #d4d4d8;
}

.main-profit {
    margin-top: 22px;
    padding: 22px;
    border-radius: 16px;
    background: rgba(255,255,255,0.08);
}

.main-profit-label {
    font-size: 14px;
    color: #d4d4d8;
    margin-bottom: 7px;
}

.main-profit-value {
    font-size: clamp(30px, 6vw, 44px);
    font-weight: 900;
    color: #86efac;
}

.formula {
    color: #a1a1aa;
    font-size: 13px;
    margin-top: 8px;
}


/* =========================
   КНОПКИ
========================= */

.actions {
    display: flex;
    gap: 10px;
    margin-top: 20px;
}

.action-button {
    border: none;
    padding: 12px 18px;
    border-radius: 10px;
    font-weight: bold;
    cursor: pointer;
}

.save {
    background: var(--purple);
    color: white;
}

.reset {
    background: #3f3f46;
    color: white;
}

.message {
    min-height: 20px;
    color: #86efac;
    font-size: 13px;
    margin-top: 12px;
}


/* =========================
   МОБИЛЬНАЯ ВЕРСИЯ
========================= */

@media (max-width: 800px) {

    .summary {
        grid-template-columns: 1fr;
    }

    .grid {
        grid-template-columns: 1fr;
    }
}

@media (max-width: 500px) {

    body {
        padding: 20px 10px 40px;
    }

    .section {
        padding: 17px;
    }

    .budget-row {
        grid-template-columns: minmax(0,1fr) 105px 38px;
    }

    .actions {
        flex-direction: column;
    }

    .action-button {
        width: 100%;
    }
}
</style>
</head>

<body>

<div class="container">

    <!-- ШАПКА -->

    <header class="header">

        <div class="badge">
            БЮДЖЕТ НЕЙРОКРЕАТОРА
        </div>

        <h1>
            Калькулятор бюджета
        </h1>

        <p>
            Укажите доходы и ежемесячные расходы.
            Калькулятор автоматически покажет,
            сколько рублей остаётся чистыми за 1 месяц.
        </p>

    </header>


    <!-- ГЛАВНАЯ СВОДКА -->

    <div class="summary">

        <div class="summary-card">

            <div class="summary-label">
                Доход за 1 месяц
            </div>

            <div
                class="summary-value income-value"
                id="summaryIncome">
                0 ₽
            </div>

        </div>


        <div class="summary-card">

            <div class="summary-label">
                Все расходы за 1 месяц
            </div>

            <div
                class="summary-value expense-value"
                id="summaryExpenses">
                0 ₽
            </div>

        </div>


        <div class="summary-card">

            <div class="summary-label">
                Чистая прибыль за 1 месяц
            </div>

            <div
                class="summary-value profit-value"
                id="summaryProfit">
                0 ₽
            </div>

        </div>

    </div>


    <!-- РАЗДЕЛЫ -->

    <div class="grid">


        <!-- ДОХОД -->

        <section class="section income-section">

            <div class="section-header">

                <div class="icon">💰</div>

                <div>
                    <h2>Доход</h2>

                    <div class="description">
                        Доходы за один месяц
                    </div>
                </div>

            </div>

            <div id="incomeRows"></div>

            <button
                class="add"
                onclick="addRow('income')">
                + Добавить источник дохода
            </button>

            <div class="section-total">

                <span>
                    Всего доходов
                </span>

                <strong id="incomeTotal">
                    0 ₽
                </strong>

            </div>

        </section>


        <!-- НЕЙРОСЕТИ -->

        <section class="section ai-section">

            <div class="section-header">

                <div class="icon">🧠</div>

                <div>
                    <h2>Нейросети</h2>

                    <div class="description">
                        Расходы на AI за месяц
                    </div>
                </div>

            </div>

            <div id="aiRows"></div>

            <button
                class="add"
                onclick="addRow('ai')">
                + Добавить нейросеть
            </button>

            <div class="section-total">

                <span>
                    Всего
                </span>

                <strong id="aiTotal">
                    0 ₽
                </strong>

            </div>

        </section>


        <!-- СОЦСЕТИ -->

        <section class="section social-section">

            <div class="section-header">

                <div class="icon">📱</div>

                <div>
                    <h2>Соцсети</h2>

                    <div class="description">
                        Расходы на продвижение за месяц
                    </div>
                </div>

            </div>

            <div id="socialRows"></div>

            <button
                class="add"
                onclick="addRow('social')">
                + Добавить расход
            </button>

            <div class="section-total">

                <span>
                    Всего
                </span>

                <strong id="socialTotal">
                    0 ₽
                </strong>

            </div>

        </section>


        <!-- ИНТЕРНЕТ -->

        <section class="section internet-section">

            <div class="section-header">

                <div class="icon">🌐</div>

                <div>
                    <h2>Интернет</h2>

                    <div class="description">
                        Интернет и онлайн-сервисы
                    </div>
                </div>

            </div>

            <div id="internetRows"></div>

            <button
                class="add"
                onclick="addRow('internet')">
                + Добавить расход
            </button>

            <div class="section-total">

                <span>
                    Всего
                </span>

                <strong id="internetTotal">
                    0 ₽
                </strong>

            </div>

        </section>

    </div>


    <!-- ФИНАНСОВЫЙ РЕЗУЛЬТАТ -->

    <section class="result">

        <h2 class="result-title">
            Итог за 1 месяц
        </h2>


        <div class="result-line">

            <span>
                Доход за месяц
            </span>

            <strong id="resultIncome">
                0 ₽
            </strong>

        </div>


        <div class="result-line">

            <span>
                Расходы на нейросети
            </span>

            <strong id="resultAI">
                0 ₽
            </strong>

        </div>


        <div class="result-line">

            <span>
                Расходы на соцсети
            </span>

            <strong id="resultSocial">
                0 ₽
            </strong>

        </div>


        <div class="result-line">

            <span>
                Интернет
            </span>

            <strong id="resultInternet">
                0 ₽
            </strong>

        </div>


        <div class="result-line">

            <span>
                Все расходы
            </span>

            <strong id="resultExpenses">
                0 ₽
            </strong>

        </div>


        <!-- ГЛАВНЫЙ ПОКАЗАТЕЛЬ -->

        <div class="main-profit">

            <div class="main-profit-label">
                ЧИСТАЯ ПРИБЫЛЬ ЗА 1 МЕСЯЦ
            </div>

            <div
                class="main-profit-value"
                id="resultProfit">
                0 ₽
            </div>

            <div class="formula">
                Доход − все расходы = чистая прибыль
            </div>

        </div>


        <div class="actions">

            <button
                class="action-button save"
                onclick="saveData()">
                Сохранить
            </button>

            <button
                class="action-button reset"
                onclick="resetData()">
                Очистить
            </button>

        </div>

        <div
            class="message"
            id="message">
        </div>

    </section>

</div>


<script>

/* ============================================
   ИСХОДНЫЕ ДАННЫЕ
============================================ */

const defaultData = {

    income: [

        {
            name: "Заказы клиентов",
            amount: 0
        },

        {
            name: "Создание AI-контента",
            amount: 0
        },

        {
            name: "Реклама / интеграции",
            amount: 0
        }

    ],


    ai: [

        {
            name: "ChatGPT",
            amount: 0
        },

        {
            name: "Генерация изображений",
            amount: 0
        },

        {
            name: "Генерация видео",
            amount: 0
        }

    ],


    social: [

        {
            name: "Реклама",
            amount: 0
        },

        {
            name: "Продвижение",
            amount: 0
        },

        {
            name: "Сервисы для соцсетей",
            amount: 0
        }

    ],


    internet: [

        {
            name: "Домашний интернет",
            amount: 0
        },

        {
            name: "Мобильная связь",
            amount: 0
        },

        {
            name: "Облачное хранилище",
            amount: 0
        }

    ]

};


let data =
    JSON.parse(
        JSON.stringify(defaultData)
    );


/* ============================================
   ФОРМАТ РУБЛЕЙ
============================================ */

function rubles(value) {

    return new Intl.NumberFormat(
        "ru-RU",
        {
            style: "currency",
            currency: "RUB",
            maximumFractionDigits: 0
        }
    ).format(value);

}


/* ============================================
   СОЗДАНИЕ СТРОК
============================================ */

function renderRows(category) {

    const container =
        document.getElementById(
            category + "Rows"
        );

    container.innerHTML = "";


    data[category].forEach(
        function(item, index) {

            const row =
                document.createElement("div");

            row.className =
                "budget-row";


            /* НАЗВАНИЕ */

            const name =
                document.createElement("input");

            name.type = "text";

            name.placeholder =
                "Название";

            name.value =
                item.name;


            name.addEventListener(
                "input",
                function() {

                    data[category][index].name =
                        this.value;

                }
            );


            /* СУММА */

            const amount =
                document.createElement("input");

            amount.type =
                "number";

            amount.min =
                "0";

            amount.step =
                "1";

            amount.placeholder =
                "₽";

            amount.className =
                "amount";


            if (item.amount > 0) {

                amount.value =
                    item.amount;

            }


            amount.addEventListener(
                "input",
                function() {

                    data[category][index].amount =
                        Number(this.value) || 0;

                    calculate();

                }
            );


            /* УДАЛЕНИЕ */

            const remove =
                document.createElement("button");

            remove.className =
                "delete";

            remove.innerHTML =
                "×";

            remove.title =
                "Удалить";


            remove.addEventListener(
                "click",
                function() {

                    removeRow(
                        category,
                        index
                    );

                }
            );


            row.appendChild(name);

            row.appendChild(amount);

            row.appendChild(remove);

            container.appendChild(row);

        }
    );

}


/* ============================================
   ДОБАВИТЬ СТРОКУ
============================================ */

function addRow(category) {

    data[category].push({

        name: "",

        amount: 0

    });


    renderRows(category);

    calculate();

}


/* ============================================
   УДАЛИТЬ СТРОКУ
============================================ */

function removeRow(category, index) {

    data[category].splice(
        index,
        1
    );


    renderRows(category);

    calculate();

}


/* ============================================
   СУММА КАТЕГОРИИ
============================================ */

function categoryTotal(category) {

    return data[category].reduce(

        function(total, item) {

            return total +
                Number(item.amount || 0);

        },

        0

    );

}


/* ============================================
   ОСНОВНОЙ РАСЧЁТ

   ФОРМУЛА:

   ЧИСТАЯ ПРИБЫЛЬ =
   ДОХОД
   - НЕЙРОСЕТИ
   - СОЦСЕТИ
   - ИНТЕРНЕТ
============================================ */

function calculate() {

    /* Доход за один месяц */

    const income =
        categoryTotal("income");


    /* Расходы за один месяц */

    const ai =
        categoryTotal("ai");

    const social =
        categoryTotal("social");

    const internet =
        categoryTotal("internet");


    /* Суммируем ВСЕ расходы */

    const expenses =
        ai +
        social +
        internet;


    /* Чистая прибыль за 1 месяц */

    const profit =
        income -
        expenses;


    /* ========================================
       СУММЫ В КАТЕГОРИЯХ
    ======================================== */

    document.getElementById(
        "incomeTotal"
    ).textContent =
        rubles(income);


    document.getElementById(
        "aiTotal"
    ).textContent =
        rubles(ai);


    document.getElementById(
        "socialTotal"
    ).textContent =
        rubles(social);


    document.getElementById(
        "internetTotal"
    ).textContent =
        rubles(internet);


    /* ========================================
       ВЕРХНИЕ КАРТОЧКИ
    ======================================== */

    document.getElementById(
        "summaryIncome"
    ).textContent =
        rubles(income);


    document.getElementById(
        "summaryExpenses"
    ).textContent =
        rubles(expenses);


    const summaryProfit =
        document.getElementById(
            "summaryProfit"
        );

    summaryProfit.textContent =
        rubles(profit);


    /* ========================================
       НИЖНЯЯ СВОДКА
    ======================================== */

    document.getElementById(
        "resultIncome"
    ).textContent =
        rubles(income);


    document.getElementById(
        "resultAI"
    ).textContent =
        rubles(ai);


    document.getElementById(
        "resultSocial"
    ).textContent =
        rubles(social);


    document.getElementById(
        "resultInternet"
    ).textContent =
        rubles(internet);


    document.getElementById(
        "resultExpenses"
    ).textContent =
        rubles(expenses);


    /* ========================================
       ЧИСТАЯ ПРИБЫЛЬ ЗА МЕСЯЦ
    ======================================== */

    const resultProfit =
        document.getElementById(
            "resultProfit"
        );


    resultProfit.textContent =
        rubles(profit);


    /* Если прибыль положительная */

    if (profit > 0) {

        resultProfit.style.color =
            "#86efac";

        summaryProfit.style.color =
            "#16a34a";

    }

    /* Если расходы больше дохода */

    else if (profit < 0) {

        resultProfit.style.color =
            "#fca5a5";

        summaryProfit.style.color =
            "#dc2626";

    }

    /* Если ровно 0 */

    else {

        resultProfit.style.color =
            "#ffffff";

        summaryProfit.style.color =
            "#7c3aed";

    }

}


/* ============================================
   СОХРАНЕНИЕ
============================================ */

function saveData() {

    localStorage.setItem(
        "creatorBudget",
        JSON.stringify(data)
    );


    const message =
        document.getElementById(
            "message"
        );


    message.textContent =
        "✓ Данные сохранены";


    setTimeout(
        function() {

            message.textContent =
                "";

        },
        2000
    );

}


/* ============================================
   ЗАГРУЗКА
============================================ */

function loadData() {

    const saved =
        localStorage.getItem(
            "creatorBudget"
        );


    if (saved) {

        try {

            data =
                JSON.parse(saved);

        }

        catch(error) {

            console.log(
                "Ошибка загрузки"
            );

        }

    }

}


/* ============================================
   ОЧИСТКА
============================================ */

function resetData() {

    const answer =
        confirm(
            "Очистить все суммы?"
        );


    if (!answer) {

        return;

    }


    data =
        JSON.parse(
            JSON.stringify(
                defaultData
            )
        );


    localStorage.removeItem(
        "creatorBudget"
    );


    renderAll();

    calculate();

}


/* ============================================
   ОТРИСОВКА
============================================ */

function renderAll() {

    renderRows("income");

    renderRows("ai");

    renderRows("social");

    renderRows("internet");

}


/* ============================================
   ЗАПУСК КАЛЬКУЛЯТОРА
============================================ */

loadData();

renderAll();

calculate();

</script>

</body>
</html>
