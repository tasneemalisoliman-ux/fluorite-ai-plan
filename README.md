<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>خطة الـ AI - Fluorite</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #FCC22D;
    --gold-light: #FFD966;
    --gold-dark: #C9960A;
    --black: #0A0A0A;
    --dark: #111111;
    --dark2: #1A1A1A;
    --dark3: #242424;
    --gray: #888888;
    --white: #F5F0E8;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'Cairo', sans-serif;
    overflow-x: hidden;
  }

  /* HEADER */
  header {
    position: relative;
    text-align: center;
    padding: 70px 20px 50px;
    overflow: hidden;
  }
  header::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(252,194,45,0.12) 0%, transparent 70%);
    pointer-events: none;
  }
  .brand-badge {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: rgba(252,194,45,0.1);
    border: 1px solid rgba(252,194,45,0.3);
    border-radius: 100px;
    padding: 6px 20px;
    font-size: 13px;
    color: var(--gold);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 28px;
  }
  .diamond { width: 8px; height: 8px; background: var(--gold); transform: rotate(45deg); display: inline-block; }
  h1 { font-size: clamp(28px, 5vw, 52px); font-weight: 900; color: var(--white); line-height: 1.2; margin-bottom: 12px; }
  h1 span { color: var(--gold); }
  .subtitle { font-size: 16px; color: var(--gray); max-width: 500px; margin: 0 auto 40px; line-height: 1.7; }

  /* RINGS */
  .ai-target { display: flex; justify-content: center; gap: 40px; flex-wrap: wrap; margin-bottom: 20px; }
  .target-ring { display: flex; flex-direction: column; align-items: center; gap: 10px; }
  .ring-wrap { position: relative; width: 100px; height: 100px; }
  .ring-wrap svg { transform: rotate(-90deg); }
  .ring-wrap .ring-bg { stroke: rgba(255,255,255,0.07); fill: none; stroke-width: 7; }
  .ring-wrap .ring-fill { fill: none; stroke: var(--gold); stroke-width: 7; stroke-linecap: round; stroke-dasharray: 251; stroke-dashoffset: 75; filter: drop-shadow(0 0 6px rgba(252,194,45,0.5)); animation: fillRing 1.5s ease forwards; }
  @keyframes fillRing { from { stroke-dashoffset: 251; } to { stroke-dashoffset: 75; } }
  .ring-num { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); font-size: 22px; font-weight: 900; color: var(--gold); }
  .ring-label { font-size: 13px; color: var(--gray); text-align: center; }

  /* DIVIDER */
  .section-divider { display: flex; align-items: center; gap: 16px; max-width: 960px; margin: 0 auto 16px; padding: 0 20px; }
  .section-divider .line { flex: 1; height: 1px; background: rgba(255,255,255,0.08); }
  .section-divider .label { font-size: 11px; letter-spacing: 3px; color: var(--gold); text-transform: uppercase; white-space: nowrap; }

  /* DEPT */
  .dept { max-width: 960px; margin: 0 auto 50px; padding: 0 20px; }
  .dept-header { display: flex; align-items: center; gap: 16px; margin-bottom: 24px; padding: 20px 24px; background: var(--dark2); border-radius: 16px; border: 1px solid rgba(252,194,45,0.15); position: relative; overflow: hidden; }
  .dept-header::before { content: ''; position: absolute; right: -20px; top: 50%; transform: translateY(-50%); width: 120px; height: 120px; background: radial-gradient(circle, rgba(252,194,45,0.07) 0%, transparent 70%); pointer-events: none; }
  .dept-icon { width: 52px; height: 52px; background: rgba(252,194,45,0.1); border: 1px solid rgba(252,194,45,0.25); border-radius: 14px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
  .dept-title { flex: 1; }
  .dept-title h2 { font-size: 20px; font-weight: 700; color: var(--white); margin-bottom: 4px; }
  .dept-title p { font-size: 13px; color: var(--gray); }
  .dept-pct { font-size: 36px; font-weight: 900; color: var(--gold); line-height: 1; }
  .dept-pct small { font-size: 14px; display: block; color: var(--gray); font-weight: 400; text-align: center; }

  /* TASKS GRID */
  .tasks-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(290px, 1fr)); gap: 14px; }

  /* TASK CARD */
  .task-card {
    background: var(--dark2);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 14px;
    overflow: hidden;
    transition: border-color 0.25s, box-shadow 0.25s;
  }
  .task-card:hover { border-color: rgba(252,194,45,0.22); }
  .task-card.open { border-color: rgba(252,194,45,0.38); box-shadow: 0 0 28px rgba(252,194,45,0.07); }

  /* CARD HEAD */
  .card-head { padding: 18px 20px; cursor: pointer; user-select: none; }
  .task-top { display: flex; align-items: flex-start; justify-content: space-between; gap: 10px; margin-bottom: 8px; }
  .task-name { font-size: 14px; font-weight: 700; color: var(--white); line-height: 1.4; flex: 1; }
  .task-badge { font-size: 10px; padding: 3px 9px; border-radius: 100px; white-space: nowrap; flex-shrink: 0; }
  .badge-free { background: rgba(74,222,128,0.12); color: #4ade80; border: 1px solid rgba(74,222,128,0.2); }
  .badge-paid { background: rgba(252,194,45,0.1); color: var(--gold); border: 1px solid rgba(252,194,45,0.2); }
  .badge-integration { background: rgba(99,102,241,0.12); color: #818cf8; border: 1px solid rgba(99,102,241,0.2); }
  .task-tool { font-size: 12px; color: var(--gold); font-weight: 600; margin-bottom: 6px; }
  .task-tool span { color: var(--gray); font-weight: 400; }
  .task-desc { font-size: 12px; color: var(--gray); line-height: 1.6; }

  /* TOGGLE ROW */
  .toggle-row { display: flex; align-items: center; justify-content: space-between; margin-top: 12px; padding-top: 10px; border-top: 1px solid rgba(255,255,255,0.05); }
  .toggle-hint { font-size: 11px; color: rgba(252,194,45,0.55); }
  .toggle-arrow { width: 22px; height: 22px; border-radius: 50%; background: rgba(252,194,45,0.1); border: 1px solid rgba(252,194,45,0.2); display: flex; align-items: center; justify-content: center; transition: transform 0.3s, background 0.2s; flex-shrink: 0; }
  .task-card.open .toggle-arrow { transform: rotate(180deg); background: rgba(252,194,45,0.2); }
  .toggle-arrow svg { width: 10px; height: 10px; }

  /* STEPS PANEL */
  .steps-panel { max-height: 0; overflow: hidden; transition: max-height 0.45s cubic-bezier(0.4,0,0.2,1); }
  .task-card.open .steps-panel { max-height: 700px; }

  .steps-inner { padding: 0 20px 20px; border-top: 1px solid rgba(252,194,45,0.08); background: rgba(252,194,45,0.02); }
  .steps-label { font-size: 10px; letter-spacing: 2px; color: rgba(252,194,45,0.45); text-transform: uppercase; padding: 12px 0 10px; display: block; }

  .step-item { display: flex; gap: 12px; padding: 8px 0; border-bottom: 1px solid rgba(255,255,255,0.04); align-items: flex-start; }
  .step-item:last-child { border-bottom: none; }
  .step-num { width: 22px; height: 22px; border-radius: 50%; background: rgba(252,194,45,0.12); border: 1px solid rgba(252,194,45,0.25); color: var(--gold); font-size: 11px; font-weight: 700; display: flex; align-items: center; justify-content: center; flex-shrink: 0; margin-top: 1px; }
  .step-content { flex: 1; }
  .step-title { font-size: 12px; font-weight: 700; color: var(--white); margin-bottom: 2px; line-height: 1.4; }
  .step-detail { font-size: 11px; color: var(--gray); line-height: 1.65; }

  /* PHASES */
  .timeline { max-width: 960px; margin: 0 auto 50px; padding: 0 20px; }
  .phase-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
  @media(max-width: 640px) { .phase-grid { grid-template-columns: 1fr; } }
  .phase-card { background: var(--dark2); border: 1px solid rgba(255,255,255,0.07); border-radius: 16px; padding: 24px; position: relative; overflow: hidden; }
  .phase-num { font-size: 60px; font-weight: 900; color: rgba(252,194,45,0.07); position: absolute; top: 10px; left: 20px; line-height: 1; font-family: 'Playfair Display', serif; }
  .phase-label { font-size: 11px; letter-spacing: 2px; color: var(--gold); text-transform: uppercase; margin-bottom: 8px; }
  .phase-title { font-size: 16px; font-weight: 700; color: var(--white); margin-bottom: 8px; }
  .phase-duration { font-size: 12px; color: var(--gray); margin-bottom: 14px; }
  .phase-items { list-style: none; }
  .phase-items li { font-size: 12px; color: var(--gray); padding: 5px 0; border-bottom: 1px solid rgba(255,255,255,0.04); display: flex; align-items: center; gap: 8px; line-height: 1.5; }
  .phase-items li::before { content: ''; width: 5px; height: 5px; background: var(--gold); border-radius: 50%; flex-shrink: 0; }

  /* ROI */
  .roi-grid { max-width: 960px; margin: 0 auto 50px; padding: 0 20px; display: grid; grid-template-columns: repeat(auto-fill, minmax(170px, 1fr)); gap: 14px; }
  .roi-card { background: var(--dark2); border: 1px solid rgba(252,194,45,0.12); border-radius: 14px; padding: 20px; text-align: center; }
  .roi-icon { font-size: 28px; margin-bottom: 10px; }
  .roi-num { font-size: 28px; font-weight: 900; color: var(--gold); margin-bottom: 4px; }
  .roi-desc { font-size: 12px; color: var(--gray); line-height: 1.5; }

  footer { text-align: center; padding: 40px 20px; border-top: 1px solid rgba(255,255,255,0.06); }
  footer .logo { font-size: 22px; font-weight: 900; color: var(--gold); letter-spacing: 3px; margin-bottom: 8px; }
  footer p { font-size: 12px; color: var(--gray); }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="brand-badge"><span class="diamond"></span>FLUORITE × AI TRANSFORMATION<span class="diamond"></span></div>
  <h1>خطة تحويل <span>70%</span> من العمليات<br>إلى الذكاء الاصطناعي</h1>
  <p class="subtitle">اضغطي على أي كارت لتظهر خطوات التنفيذ التفصيلية</p>
  <div class="ai-target">
    <div class="target-ring">
      <div class="ring-wrap">
        <svg width="100" height="100" viewBox="0 0 100 100"><circle class="ring-bg" cx="50" cy="50" r="40"/><circle class="ring-fill" cx="50" cy="50" r="40"/></svg>
        <div class="ring-num">70%</div>
      </div>
      <div class="ring-label">الهدف الكلي</div>
    </div>
    <div class="target-ring">
      <div class="ring-wrap">
        <svg width="100" height="100" viewBox="0 0 100 100"><circle class="ring-bg" cx="50" cy="50" r="40"/><circle class="ring-fill" cx="50" cy="50" r="40" style="stroke-dashoffset:80"/></svg>
        <div class="ring-num">3</div>
      </div>
      <div class="ring-label">أقسام مستهدفة</div>
    </div>
    <div class="target-ring">
      <div class="ring-wrap">
        <svg width="100" height="100" viewBox="0 0 100 100"><circle class="ring-bg" cx="50" cy="50" r="40"/><circle class="ring-fill" cx="50" cy="50" r="40" style="stroke-dashoffset:130"/></svg>
        <div class="ring-num">18</div>
      </div>
      <div class="ring-label">مهمة مؤتمتة</div>
    </div>
    <div class="target-ring">
      <div class="ring-wrap">
        <svg width="100" height="100" viewBox="0 0 100 100"><circle class="ring-bg" cx="50" cy="50" r="40"/><circle class="ring-fill" cx="50" cy="50" r="40" style="stroke-dashoffset:168"/></svg>
        <div class="ring-num">3</div>
      </div>
      <div class="ring-label">مراحل تنفيذ</div>
    </div>
  </div>
</header>

<!-- ═══ DEPT 1: MARKETING ═══ -->
<div class="section-divider"><div class="line"></div><div class="label">القسم الأول</div><div class="line"></div></div>
<div class="dept">
  <div class="dept-header">
    <div class="dept-icon">📣</div>
    <div class="dept-title">
      <h2>قسم التسويق والمحتوى</h2>
      <p>إنتاج المحتوى · الإعلانات · إدارة السوشيال ميديا · التصميم</p>
    </div>
    <div class="dept-pct">75%<small>أتمتة مستهدفة</small></div>
  </div>
  <div class="tasks-grid">

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">كتابة كابشن السوشيال ميديا</div><span class="task-badge badge-paid">مدفوع</span></div>
        <div class="task-tool">Claude / ChatGPT <span>· إنشاء المحتوى</span></div>
        <div class="task-desc">كتابة كابشن عربي بأسلوب Fluorite الراقي لكل منصة بشكل يومي أو أسبوعي</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">اعملي Brand Voice Document</div><div class="step-detail">اكتبي فيه كيف تتكلم Fluorite — الكلمات اللي تستخدمها، اللي تتجنبها، الـ tone (راقي، دافئ، عربي أصيل)</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اعملي Prompt Template ثابت</div><div class="step-detail">Prompt جاهز فيه: اسم المنتج + المنصة + الهدف (engagement/sale/awareness) — تنسخيه وتعبئيه كل مرة</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">جربي Claude.ai أو ChatGPT Plus</div><div class="step-detail">ابدئي بـ free plan وشوفي النتائج، لو عاجبك اشتركي في Plus (~$20/شهر) للجودة العالية</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">اعملي Content Calendar أسبوعي</div><div class="step-detail">جلسة واحدة كل أسبوع تولدي فيها كل الكابشن للأسبوع الجاي دفعة واحدة — توفير 80% من الوقت</div></div></div>
        <div class="step-item"><div class="step-num">5</div><div class="step-content"><div class="step-title">راجعي وعدلي قبل النشر</div><div class="step-detail">الـ AI يولد المسودة، إنتي تراجعي في دقيقتين وتضيفي أي تفصيلة خاصة بالمنتج</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">توليد صور المنتجات وإعلانات الفيجوال</div><span class="task-badge badge-paid">مدفوع</span></div>
        <div class="task-tool">Midjourney / Ideogram <span>· توليد الصور</span></div>
        <div class="task-desc">تصميم فيجوال راقي للمجوهرات والإعلانات بدون فوتوغرافر في كل مرة</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">اشتركي في Ideogram (أسهل للمبتدئين)</div><div class="step-detail">ideogram.ai مجاني بحد معين، ممتاز للفيجوال الراقي. بديل: Midjourney ~$10/شهر</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اعملي Moodboard لـ Fluorite</div><div class="step-detail">اجمعي 10-15 صورة توضح الـ aesthetic المطلوب (ألوان، خلفيات، إضاءة) كمرجع للـ prompts</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">اكتبي Prompt Template للمجوهرات</div><div class="step-detail">مثال: "luxury gold vermeil jewelry, black marble background, soft studio lighting, editorial style, high-end Saudi brand"</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">ولدي وانتقي أحسن 2-3 صور</div><div class="step-detail">كل prompt بيدي 4 خيارات — انتقي الأفضل وعدلي عليه بـ Canva أو Adobe Express</div></div></div>
        <div class="step-item"><div class="step-num">5</div><div class="step-content"><div class="step-title">أضيفي الـ branding (لوجو + ألوان)</div><div class="step-detail">خلي Template جاهز في Canva تحطي فيه الصورة المولدة مع لوجو Fluorite والـ CTA</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">جدولة ونشر المحتوى تلقائياً</div><span class="task-badge badge-free">مجاني جزئياً</span></div>
        <div class="task-tool">Buffer / Later / Meta Suite <span>· الجدولة</span></div>
        <div class="task-desc">جدولة المنشورات على كل المنصات أسبوعياً بدون تدخل يدوي يومي</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">اختاري الأداة المناسبة</div><div class="step-detail">Meta Business Suite مجاني لـ IG + Facebook. Buffer مجاني لـ 3 منصات. Later ممتاز للصور (~$18/شهر)</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">وصّلي كل الحسابات</div><div class="step-detail">Instagram, TikTok, Snapchat — اتبعي خطوات الربط في الأداة (عادةً 5 دقايق لكل منصة)</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">حددي مواعيد النشر الأمثل</div><div class="step-detail">بناءً على تقارير المنصات: عادةً الثلاثاء-الخميس 7-9م لـ الجمهور السعودي</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">اعملي جلسة جدولة أسبوعية</div><div class="step-detail">كل أحد: ارفعي الصور + الكابشن للأسبوع كله دفعة واحدة وجدوليهم على مدار الأسبوع</div></div></div>
        <div class="step-item"><div class="step-num">5</div><div class="step-content"><div class="step-title">فعّلي التقارير التلقائية</div><div class="step-detail">اضبطي weekly report يوصلك كل إثنين بأداء الأسبوع اللي فات (reach, engagement, clicks)</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">كتابة وصف المنتجات على المتاجر</div><span class="task-badge badge-paid">مدفوع</span></div>
        <div class="task-tool">Claude / ChatGPT <span>· SEO + محتوى</span></div>
        <div class="task-desc">كتابة وصف جذاب وSEO-friendly لكل منتج على Salla وكل المنصات</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">اعملي Sheet بكل تفاصيل المنتجات</div><div class="step-detail">اسم المنتج، المواد، المقاسات، السعر، المميزات — ده المدخل اللي هتديه للـ AI</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اكتبي Prompt متخصص للوصف</div><div class="step-detail">مثال: "اكتبي وصف منتج راقي بالعربية لـ [اسم المنتج]، المادة: Gold Vermeil 18K، الجمهور: سيدات سعوديات 25-40"</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">ولدي الوصف دفعة واحدة</div><div class="step-detail">اعملي كل المنتجات في جلسة واحدة — بدل ما تكتبي منتج منتج، ابعتي لـ Claude قائمة كاملة</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">انسخي على Salla مباشرة</div><div class="step-detail">اتأكدي إن الوصف فيه كلمات مفتاحية (مجوهرات ذهبية، Gold Vermeil، هدايا فاخرة) لتحسين SEO</div></div></div>
        <div class="step-item"><div class="step-num">5</div><div class="step-content"><div class="step-title">اعملي A/B Test على أفضل وصفين</div><div class="step-detail">لأكثر المنتجات مبيعاً، جربي نسختين من الوصف وشوفي أيهم يحول أكثر</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">تحليل أداء المحتوى والتقارير</div><span class="task-badge badge-integration">تكامل</span></div>
        <div class="task-tool">Notion AI / Looker Studio <span>· التحليل</span></div>
        <div class="task-desc">تقارير أسبوعية تلقائية عن أداء كل منشور ومقارنة المنصات</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">وصّلي Meta Insights بـ Looker Studio</div><div class="step-detail">Looker Studio مجاني من Google — فيه Connector جاهز لـ Facebook/Instagram يربطهم في دقايق</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اعملي Dashboard موحد</div><div class="step-detail">Reach + Engagement + Click-through لكل منصة في مكان واحد بدل ما تدخلي كل منصة لوحدها</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">اضبطي Email Report أسبوعي</div><div class="step-detail">Looker Studio بيبعت الـ Dashboard PDF على إيميلك أوتوماتيك كل إثنين الصبح</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">استخدمي Claude لتحليل النتائج</div><div class="step-detail">انسخي الأرقام لـ Claude وقوليله "حللي الأداء ده وقوليني إيه أفضل نوع محتوى الأسبوع اللي فات"</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">إنشاء فيديوهات المنتجات القصيرة</div><span class="task-badge badge-paid">مدفوع</span></div>
        <div class="task-tool">Runway / Kling AI <span>· توليد الفيديو</span></div>
        <div class="task-desc">ريلز وتيك توك قصيرة للمنتجات بالذكاء الاصطناعي دون تصوير في كل مرة</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">جربي Kling AI أو Runway Gen-3</div><div class="step-detail">Kling.ai ممتاز للجودة العالية (~$10/شهر). Runway بيدي 125 credits مجاني للبداية</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">ارفعي صورة المنتج وحوليها لفيديو</div><div class="step-detail">Image-to-Video: ارفعي صورة المجوهر + اكتبي الحركة المطلوبة مثل "slow rotation, sparkle effect, luxury lighting"</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">أضيفي موسيقى ونص بـ CapCut</div><div class="step-detail">CapCut مجاني — ارفعي الفيديو المولد، أضيفي موسيقى ترند + اسم المنتج + رابط المتجر</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">انشري على TikTok و Reels</div><div class="step-detail">الفيديوهات 7-15 ثانية هي الأفضل أداءً — اهتمي بالثانية الأولى عشان توقف السكرول</div></div></div>
      </div></div>
    </div>

  </div>
</div>

<!-- ═══ DEPT 2: SALES ═══ -->
<div class="section-divider"><div class="line"></div><div class="label">القسم الثاني</div><div class="line"></div></div>
<div class="dept">
  <div class="dept-header">
    <div class="dept-icon">💰</div>
    <div class="dept-title">
      <h2>قسم المبيعات</h2>
      <p>متابعة العملاء · العروض · الطلبات · التحليل · التقارير</p>
    </div>
    <div class="dept-pct">70%<small>أتمتة مستهدفة</small></div>
  </div>
  <div class="tasks-grid">

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">إشعارات الطلبات الجديدة فوراً</div><span class="task-badge badge-integration">تكامل</span></div>
        <div class="task-tool">Zapier + WhatsApp <span>· الإشعارات</span></div>
        <div class="task-desc">أي طلب جديد على أي منصة يوصل رسالة واتساب للفريق فوراً مع كل تفاصيل الطلب</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">افتحي حساب Zapier مجاني</div><div class="step-detail">zapier.com — الـ free plan يكفي لـ 100 مهمة/شهر كبداية ممتازة</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اعملي Zap: Salla → WhatsApp</div><div class="step-detail">Trigger: "New Order in Salla" — Action: "Send WhatsApp Message" عبر Twilio أو WhatsApp Business API</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">صممي قالب الرسالة</div><div class="step-detail">مثال: "🛍 طلب جديد! العميل: {{name}} | المنتج: {{items}} | القيمة: {{total}} ر.س | المدينة: {{city}}"</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">كرري لكل منصة</div><div class="step-detail">اعملي نفس الـ Zap لـ Bleems, Bansie, TheChefz, PIK — كل واحدة Trigger منفصل</div></div></div>
        <div class="step-item"><div class="step-num">5</div><div class="step-content"><div class="step-title">اختبري الـ Zap قبل الإطلاق</div><div class="step-detail">اعملي طلب تجريبي وتأكدي إن الرسالة وصلت صح في خلال 30 ثانية</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">متابعة العملاء اللي ما أكملوا الشراء</div><span class="task-badge badge-integration">تكامل</span></div>
        <div class="task-tool">Salla Automation + Zapier <span>· Abandoned Cart</span></div>
        <div class="task-desc">رسائل تلقائية للعملاء اللي تركوا المنتج في السلة بدون إتمام الطلب</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">فعّلي Abandoned Cart في Salla</div><div class="step-detail">لوحة تحكم Salla ← التسويق ← الأتمتة ← سلة متروكة — فعّليها وحدّدي وقت الانتظار (1-3 ساعات)</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اكتبي رسالة SMS/WhatsApp مقنعة</div><div class="step-detail">مثال: "مرحباً {{name}}، لاحظنا إنك تركتِ {{product}} في سلتك 💛 أنهي طلبك الآن وسنوصله خلال ساعتين"</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">أضيفي كود خصم محدود الوقت</div><div class="step-detail">خصم 10% صالح 24 ساعة بيزيد معدل إكمال الطلب بشكل ملحوظ — اعمليه في Salla Coupons</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">اعملي sequence من 3 رسائل</div><div class="step-detail">رسالة 1 بعد ساعة (تذكير) → رسالة 2 بعد 24 ساعة (خصم) → رسالة 3 بعد 48 ساعة (آخر فرصة)</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">تقارير المبيعات اليومية والأسبوعية</div><span class="task-badge badge-free">مجاني جزئياً</span></div>
        <div class="task-tool">Google Sheets + AI <span>· التقارير</span></div>
        <div class="task-desc">جمع بيانات المبيعات من كل المنصات تلقائياً وتوليد تقرير موحد</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">اعملي Master Sheet للمبيعات</div><div class="step-detail">Google Sheet فيه Columns: التاريخ، المنصة، المنتج، الكمية، القيمة، المدينة — مصدر البيانات الموحد</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اربطي Salla بـ Google Sheets عبر Zapier</div><div class="step-detail">كل طلب جديد على Salla يتضاف تلقائياً صف جديد في الـ Sheet بدون تدخل يدوي</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">اعملي Dashboard في Looker Studio</div><div class="step-detail">وصّلي الـ Sheet بـ Looker Studio واعملي charts للمبيعات اليومية وأكثر المنتجات وأكثر المدن</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">اضبطي Email Report أسبوعي تلقائي</div><div class="step-detail">Looker Studio ← Share ← Schedule Email Delivery — كل إثنين الصبح يوصل PDF للمدير تلقائياً</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">توصيات المنتجات الشخصية للعملاء</div><span class="task-badge badge-paid">مدفوع</span></div>
        <div class="task-tool">Salla AI / Klaviyo <span>· Personalization</span></div>
        <div class="task-desc">اقتراح منتجات لكل عميل بناءً على تاريخ شرائه وتصرفاته على الموقع</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">فعّلي "المنتجات المشابهة" في Salla</div><div class="step-detail">إعدادات Salla ← المنتجات ← توصيات ذكية — فعّليها وهي هتشتغل تلقائياً على صفحات المنتجات</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">جزّئي قاعدة العملاء</div><div class="step-detail">أول مرة شراء / عميل متكرر / عميل VIP (أكثر من 3 طلبات) — لكل شريحة رسالة مختلفة</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">ابعتي رسالة Cross-sell بعد كل شراء</div><div class="step-detail">"عشان اشتريتِ [خاتم الورد]، قد يعجبك [طوق الذهب 18K]" + صورة + رابط مباشر</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">لو عايزة تتقدمي: ربطي Klaviyo</div><div class="step-detail">Klaviyo بيتكامل مع Salla ويدي personalization متقدم — ابدئي بالـ free plan (500 عميل)</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">تسعير ديناميكي وعروض مؤقتة</div><span class="task-badge badge-integration">تكامل</span></div>
        <div class="task-tool">Salla Promotions + Zapier <span>· Dynamic Pricing</span></div>
        <div class="task-desc">تفعيل وإيقاف العروض تلقائياً في مواعيد محددة بدون تدخل يدوي</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">اعملي Coupons جاهزة في Salla</div><div class="step-detail">Salla ← التسويق ← الكوبونات — اعملي كوبون لكل مناسبة (اليوم الوطني، الجمعة البيضاء، عيد الأم)</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اضبطي تاريخ البداية والنهاية</div><div class="step-detail">كل كوبون له Expiry Date — Salla بتوقفه تلقائياً ما تحتاجي تتذكري تطفّيه يدوياً</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">اعملي Zapier Zap للإشعار التلقائي</div><div class="step-detail">Trigger: Schedule (موعد بداية العرض) → Action: إرسال WhatsApp Broadcast للعملاء بكود الخصم</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">تابعي الأداء في real-time</div><div class="step-detail">Salla Analytics بتوضح كم كوبون انستخدم ومتى — استخدميه تحددي أنجح أوقات العروض</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">تتبع المخزون وإشعارات النفاد</div><span class="task-badge badge-integration">تكامل</span></div>
        <div class="task-tool">Stora + Zapier <span>· Inventory AI</span></div>
        <div class="task-desc">إشعار فوري لما أي منتج يوصل لحد معين وربطه بنظام إعادة الطلب من Stora</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">حددي Low Stock Threshold لكل منتج</div><div class="step-detail">مثلاً: لو المخزون وصل 5 قطع → إشعار. حدديه في Salla ← المنتجات ← تنبيهات المخزون</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اعملي Zap: Low Stock → WhatsApp</div><div class="step-detail">Trigger: "Low inventory alert" → Action: رسالة للمسؤول "⚠️ المنتج X وصل لـ 5 قطع فقط — وقت إعادة الطلب"</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">وثّقي عملية إعادة الطلب مع Stora</div><div class="step-detail">اعملي SOP واضح: مين يطلب؟ في كم يوم؟ الكميات الدنيا؟ خلّيها معروفة للفريق</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">أخفي المنتج تلقائياً لو نفد</div><div class="step-detail">في Salla: اضبطي "إخفاء المنتج عند نفاد المخزون" — بيمنع العملاء يطلبوا منتجات غير متاحة</div></div></div>
      </div></div>
    </div>

  </div>
</div>

<!-- ═══ DEPT 3: CUSTOMER SERVICE ═══ -->
<div class="section-divider"><div class="line"></div><div class="label">القسم الثالث</div><div class="line"></div></div>
<div class="dept">
  <div class="dept-header">
    <div class="dept-icon">💎</div>
    <div class="dept-title">
      <h2>قسم خدمة العملاء</h2>
      <p>الردود · الشكاوى · الاستفسارات · متابعة الطلبات · التقييمات</p>
    </div>
    <div class="dept-pct">65%<small>أتمتة مستهدفة</small></div>
  </div>
  <div class="tasks-grid">

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">Chatbot لخدمة العملاء 24/7</div><span class="task-badge badge-paid">مدفوع</span></div>
        <div class="task-tool">Tidio AI / Salla Chat <span>· Chatbot</span></div>
        <div class="task-desc">ردود تلقائية فورية على الأسئلة الشائعة (الأسعار، التوصيل، المقاسات، الاسترجاع)</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">اجمعي أكثر 20 سؤال متكرر</div><div class="step-detail">راجعي رسائل WhatsApp والـ DMs القديمة — اكتبي الأسئلة الأكثر تكراراً وإجاباتها الصحيحة</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اشتركي في Tidio أو Salla Chat</div><div class="step-detail">tidio.com فيه free plan يكفي للبداية. أو استخدمي الـ Chat المدمج في Salla مباشرة</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">برمجي الـ FAQ flows</div><div class="step-detail">اعملي شجرة: "ما طبيعة استفسارك؟" ← التوصيل / الأسعار / الاسترجاع / أخرى — لكل فرع رد جاهز</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">اكتبي الردود بـ tone Fluorite</div><div class="step-detail">استخدمي Claude لكتابة ردود راقية ودافئة تعكس شخصية البراند — مش ردود آلية جافة</div></div></div>
        <div class="step-item"><div class="step-num">5</div><div class="step-content"><div class="step-title">اضبطي Handoff للموظف البشري</div><div class="step-detail">لو الـ Bot ما قدرش يرد → يحول للموظف المسؤول مع ملخص المحادثة تلقائياً</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">ردود تلقائية على الكومنتات</div><span class="task-badge badge-paid">مدفوع</span></div>
        <div class="task-tool">ManyChat / MetaAI <span>· Social Automation</span></div>
        <div class="task-desc">رد تلقائي على كومنتات إنستجرام وتيك توك مع توجيه العميل للمتجر</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">افتحي حساب ManyChat</div><div class="step-detail">manychat.com — ابدئي بالـ free plan. وصّليه بـ Instagram Business + Facebook Page</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اعملي Keyword Triggers</div><div class="step-detail">لو حد كتب "السعر" أو "كيف أطلب" أو "متوفر؟" في الكومنتات → يجيه DM تلقائي برابط المتجر</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">اعملي Story Reply Automation</div><div class="step-detail">لو حد رد على Story المنتج بـ "كيف" أو "أريد" → يجيه رسالة مباشرة بتفاصيل المنتج ورابطه</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">صممي DM Flow بسيط</div><div class="step-detail">رسالة ترحيب → "هل تريدين الشراء أو الاستفسار؟" → يوجهها للمتجر أو الواتساب حسب الاختيار</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">تتبع الطلبات تلقائياً للعملاء</div><span class="task-badge badge-integration">تكامل</span></div>
        <div class="task-tool">Salla + WhatsApp Bot <span>· Order Tracking</span></div>
        <div class="task-desc">العميل يبعث رقم طلبه ويجيه كل التفاصيل تلقائياً بدون موظف</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">فعّلي إشعارات Salla التلقائية</div><div class="step-detail">Salla ← الإشعارات — فعّلي: تأكيد الطلب، قيد التجهيز، تم الشحن، تم التوصيل — كل واحدة برسالة SMS/WhatsApp</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">خصّصي نصوص الرسائل</div><div class="step-detail">اكتبي رسائل بـ tone Fluorite الراقي — مش الرسائل الافتراضية الجافة. مثال: "طلبك في طريقه إليكِ ✨"</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">أضيفي رابط التتبع في كل رسالة</div><div class="step-detail">رابط Stora أو شركة الشحن مباشرة في الرسالة — العميل يتابع بنفسه بدون ما يسأل</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">اعملي WhatsApp Bot للاستعلام</div><div class="step-detail">لو العميل بعت رقم الطلب على الواتساب → Zapier يستعلم من Salla ويرجع له الحالة تلقائياً</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">جمع وتحليل تقييمات العملاء</div><span class="task-badge badge-free">مجاني جزئياً</span></div>
        <div class="task-tool">Salla Reviews + AI Analysis <span>· Sentiment</span></div>
        <div class="task-desc">تجميع كل التقييمات وتحليل المشاعر ومعرفة أكثر نقاط الشكوى تكراراً</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">فعّلي طلب التقييم في Salla</div><div class="step-detail">Salla ← الإشعارات ← بعد التوصيل — بعد يوم من الاستلام يجيه SMS/WhatsApp يطلب التقييم</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اجمعي كل التقييمات شهرياً</div><div class="step-detail">نزّلي Export لكل التقييمات من Salla وكذلك من المنصات الأخرى في Sheet واحد</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">حلّليها بـ Claude دفعة واحدة</div><div class="step-detail">الصقي كل التقييمات وقولي لـ Claude: "حللي دي وقوليلي أكثر 5 نقاط شكوى وأكثر 5 نقاط إيجابية"</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">حوّلي الملاحظات لإجراءات</div><div class="step-detail">اعملي Action List شهرية من التقارير — كل مشكلة متكررة ليها حل يتنفذ في الشهر الجاي</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">رسائل ما بعد الشراء والتقييم</div><span class="task-badge badge-integration">تكامل</span></div>
        <div class="task-tool">Salla + WhatsApp <span>· Post Purchase</span></div>
        <div class="task-desc">رسالة تلقائية بعد استلام الطلب تطلب التقييم وتعرض منتجات مشابهة</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">اعملي Post-Purchase Sequence</div><div class="step-detail">رسالة 1 (بعد التوصيل بيوم): "كيف وصل طلبك؟ 💛 نتمنى يكون أعجبك" + رابط التقييم</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">أضيفي Cross-sell في الرسالة</div><div class="step-detail">رسالة 2 (بعد أسبوع): "عشان اشتريتِ الخاتم، قد يعجبك الطوق المتناسق معه" + صورة + رابط</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">اعملي VIP Loyalty Message</div><div class="step-detail">بعد الطلب الثالث: "أنتِ من عملاء Fluorite المميزين ✨ هدية خصم 15% على طلبك القادم"</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">شغّلي كل ده من Salla Automation</div><div class="step-detail">Salla ← التسويق ← الأتمتة — فيها حالات Post Delivery جاهزة، شغّليها وخصّصي النصوص</div></div></div>
      </div></div>
    </div>

    <div class="task-card">
      <div class="card-head" onclick="toggleCard(this)">
        <div class="task-top"><div class="task-name">تصنيف وتوجيه الرسائل للفريق</div><span class="task-badge badge-paid">مدفوع</span></div>
        <div class="task-tool">AI Triage + Notion <span>· Smart Routing</span></div>
        <div class="task-desc">AI يصنف كل رسالة ويوجهها للشخص المناسب في الفريق تلقائياً</div>
        <div class="toggle-row"><span class="toggle-hint">▸ خطوات التنفيذ</span><div class="toggle-arrow"><svg viewBox="0 0 10 6" fill="none"><path d="M1 1l4 4 4-4" stroke="#FCC22D" stroke-width="1.5" stroke-linecap="round"/></svg></div></div>
      </div>
      <div class="steps-panel"><div class="steps-inner">
        <span class="steps-label">خطوات التنفيذ</span>
        <div class="step-item"><div class="step-num">1</div><div class="step-content"><div class="step-title">حددي تصنيفات الرسائل</div><div class="step-detail">5 تصنيفات: استفسار منتج / تتبع طلب / شكوى / استرجاع / أخرى — لكل تصنيف مسؤول محدد</div></div></div>
        <div class="step-item"><div class="step-num">2</div><div class="step-content"><div class="step-title">اعملي Notion Database للتكتات</div><div class="step-detail">Notion ← New Database: رقم التكت، التصنيف، العميل، الحالة، المسؤول، الوقت — مركز إدارة CS</div></div></div>
        <div class="step-item"><div class="step-num">3</div><div class="step-content"><div class="step-title">اربطي الواتساب بـ Zapier + Notion</div><div class="step-detail">كل رسالة واتساب جديدة → Zapier يضيفها في Notion تلقائياً مع بيانات العميل</div></div></div>
        <div class="step-item"><div class="step-num">4</div><div class="step-content"><div class="step-title">استخدمي Claude API للتصنيف التلقائي</div><div class="step-detail">خطوة متقدمة: Zapier يبعث نص الرسالة لـ Claude API يرجع التصنيف تلقائياً ويحدد الأولوية</div></div></div>
        <div class="step-item"><div class="step-num">5</div><div class="step-content"><div class="step-title">اضبطي SLA لكل تصنيف</div><div class="step-detail">شكوى: رد في ساعة | استفسار: رد في 3 ساعات | استرجاع: رد في 24 ساعة — مع تنبيه تلقائي لو تأخر</div></div></div>
      </div></div>
    </div>

  </div>
</div>

<!-- PHASES -->
<div class="section-divider"><div class="line"></div><div class="label">خطة التنفيذ</div><div class="line"></div></div>
<div class="timeline">
  <div class="phase-grid">
    <div class="phase-card">
      <div class="phase-num">01</div>
      <div class="phase-label">المرحلة الأولى · شهر 1-2</div>
      <div class="phase-title">الأساس والأتمتة الفورية</div>
      <div class="phase-duration">Quick wins تحقق نتائج فورية</div>
      <ul class="phase-items">
        <li>Zapier + WhatsApp لإشعارات الطلبات</li>
        <li>Chatbot خدمة العملاء الأساسي</li>
        <li>Claude لكتابة وصف المنتجات</li>
        <li>جدولة المحتوى على Buffer</li>
        <li>تقارير المبيعات الأسبوعية التلقائية</li>
      </ul>
    </div>
    <div class="phase-card">
      <div class="phase-num">02</div>
      <div class="phase-label">المرحلة الثانية · شهر 3-4</div>
      <div class="phase-title">توسيع التكاملات</div>
      <div class="phase-duration">ربط الأنظمة ببعضها</div>
      <ul class="phase-items">
        <li>ManyChat للردود على السوشيال ميديا</li>
        <li>Abandoned Cart Automation على Salla</li>
        <li>توليد الفيجوال بـ Midjourney</li>
        <li>تتبع الطلبات عبر WhatsApp Bot</li>
        <li>AI تحليل تقييمات العملاء</li>
      </ul>
    </div>
    <div class="phase-card">
      <div class="phase-num">03</div>
      <div class="phase-label">المرحلة الثالثة · شهر 5-6</div>
      <div class="phase-title">الأتمتة المتقدمة</div>
      <div class="phase-duration">AI يدير العمليات بشكل كامل</div>
      <ul class="phase-items">
        <li>Personalization وتوصيات المنتجات</li>
        <li>توليد الفيديوهات القصيرة بـ AI</li>
        <li>تسعير ديناميكي وعروض ذكية</li>
        <li>تصنيف وتوجيه الرسائل تلقائياً</li>
        <li>Dashboard موحد لكل المنصات</li>
      </ul>
    </div>
  </div>
</div>

<!-- ROI -->
<div class="section-divider"><div class="line"></div><div class="label">النتائج المتوقعة</div><div class="line"></div></div>
<div class="roi-grid">
  <div class="roi-card"><div class="roi-icon">⏰</div><div class="roi-num">-60%</div><div class="roi-desc">تخفيض وقت إنتاج المحتوى اليدوي</div></div>
  <div class="roi-card"><div class="roi-icon">⚡</div><div class="roi-num">24/7</div><div class="roi-desc">خدمة عملاء متاحة دون موظف بدوام كامل</div></div>
  <div class="roi-card"><div class="roi-icon">📈</div><div class="roi-num">+25%</div><div class="roi-desc">زيادة معدل الرد على الاستفسارات والتحويل</div></div>
  <div class="roi-card"><div class="roi-icon">💸</div><div class="roi-num">-40%</div><div class="roi-desc">تخفيض تكاليف العمالة في المهام المتكررة</div></div>
  <div class="roi-card"><div class="roi-icon">🎯</div><div class="roi-num">×3</div><div class="roi-desc">زيادة كمية المحتوى المنتج بنفس الفريق</div></div>
</div>

<footer>
  <div class="logo">FLUORITE ◆</div>
  <p>خطة تحويل العمليات بالذكاء الاصطناعي · 2025</p>
</footer>

<script>
  function toggleCard(headEl) {
    const card = headEl.closest('.task-card');
    const isOpen = card.classList.contains('open');
    document.querySelectorAll('.task-card.open').forEach(c => c.classList.remove('open'));
    if (!isOpen) {
      card.classList.add('open');
      setTimeout(() => card.scrollIntoView({ behavior: 'smooth', block: 'nearest' }), 50);
    }
  }
</script>
</body>
</html>
