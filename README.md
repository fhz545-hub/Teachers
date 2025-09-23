<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1"/>
<title>نموذج تقييم الاداء الوظيفي للمعلمين للعام ١٤٤٧هـ</title>

<!-- خطوط -->
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;600;700&family=Cairo:wght@400;600;700&display=swap" rel="stylesheet">

<!-- مكتبات الحفظ -->
<script src="https://cdn.jsdelivr.net/npm/html2canvas@1.4.1/dist/html2canvas.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/jspdf@2.5.1/dist/jspdf.umd.min.js"></script>

<style>
:root{
  --teal:#0f4c46; --ink:#103330; --muted:#456A66; --border:#e5efec; --bg:#f7fbfa;
  --green:#22c55e; --amber:#f59e0b; --red:#ef4444;
}
html,body{margin:0!important;padding:0!important;background:#fff;color:var(--ink);
  -webkit-text-size-adjust:100%; print-color-adjust: exact; -webkit-print-color-adjust: exact;
  font-family:"Tajawal",system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue",Arial}
*{box-sizing:border-box}

#page{width:794px; min-height:1123px; margin:0 auto; background:#fff;}
.wrap{max-width:100%; margin-inline:auto; padding:6px 10px}

/* الهيدر */
header{text-align:center;margin:0 0 6px}
header .topline{font-weight:700;color:var(--teal);font-size:13px;line-height:1.25}
header .schooltitle{display:flex;gap:6px;align-items:center;justify-content:center;flex-wrap:wrap;margin-top:3px}
header .schooltitle h1{font-size:14.5px;color:var(--teal);margin:0}
.badge{background:#eaf4f1;border:1px solid var(--border);padding:4px 8px;border-radius:10px;font-weight:700;color:#0b2f2c;font-size:11.2px}

/* تعريف */
.note{margin:6px 0 8px;color:var(--muted);background:#f2f8f6;border:1px solid var(--border);
  border-radius:10px;padding:7px 8px;line-height:1.55;font-size:12px}

/* صف اختيار المعلّم */
.teacher-row{display:grid;grid-template-columns:1fr;gap:6px;margin:4px 0}
.f{background:#fbfdfc;border:1px solid var(--border);border-radius:10px;padding:6px 8px}
.f label{display:block;font-size:10px;color:#4b6864;margin-bottom:2px}
.f select{width:100%;height:34px;border:1px solid #cfe1dd;border-radius:8px;background:#fff;font:inherit;font-size:13px;padding:0 10px;}

/* بيانات */
.info-row{display:grid;grid-template-columns:1.1fr 1fr 1fr 0.9fr;gap:6px;margin:4px 0 6px}
.f input,.f .mini-select{width:100%;height:34px;border:1px solid #cfe1dd;border-radius:8px;background:#fff;
  font:inherit;font-size:13px;line-height:34px;padding:0 10px;color:#103330}
.f input::placeholder{color:#9cb3af; opacity:.9}
.f .mini-select{appearance:auto}

/* المؤشر */
.bar-row{display:flex;align-items:center;gap:6px;margin:6px 0 2px}
.chip{background:#f2f7f6;border:1px solid var(--border);padding:6px 8px;border-radius:10px;font-weight:700;color:#09312d;min-width:135px;text-align:center;font-size:11.5px}
.meter{position:relative;height:16px;flex:1;background:#eaf1ef;border:1px solid var(--border);border-radius:12px;overflow:hidden}
.fill{position:absolute;inset:3px;border-radius:10px;background:linear-gradient(90deg,var(--green) 0%, #7ad957 25%, var(--amber) 55%, #ff914d 75%, var(--red) 100%);}
.thumb{position:absolute;top:50%;transform:translate(-50%,-50%);width:14px;height:14px;border-radius:50%;
  background:#fff;border:3px solid #33524e;box-shadow:0 1px 5px rgba(0,0,0,.15)}
.scale{position:relative;height:12px;margin-top:2px;font-weight:700;color:#2a4743;font-size:11px}
.scale span{position:absolute;transform:translateX(-50%)}
.scale .t5{left:0%}.scale .t4{left:25%}.scale .t3{left:50%}.scale .t2{left:75%}.scale .t1{left:100%}

/* الجدول */
table{width:100%;border-collapse:separate;border-spacing:0 4px}
th,td{background:#fbfdfc;border:1px solid var(--border);padding:5px 7px;vertical-align:middle;font-size:12px}
th{background:var(--teal);color:#fff;text-align:center;font-size:11.8px;line-height:1.2;padding:4px 6px}
th:first-child,td:first-child{border-radius:8px 0 0 8px}
th:last-child, td:last-child{border-radius:0 8px 8px 0}

/* الدرجة والوزن */
.w-tight{width:72px;text-align:center}
.w{width:64px;text-align:center}
th .sub{display:block;font-size:10px;opacity:.9;margin-top:2px}

select.grade{width:62px;height:28px;text-align:center;border:1px solid #cfe1dd;border-radius:8px;background:#fff;font-size:12.3px}

/* نص الأمثلة */
td.brief{font-size:12px;color:#2a4743;line-height:1.45}

/* القوة/التطوير */
.cards{display:grid;grid-template-columns:1fr 1fr;gap:6px;margin-top:6px}
.card{background:#fff;border:1px solid var(--border);border-radius:12px;padding:7px 8px;min-height:56px}
.card h3{margin:0 0 4px;font-size:13px}
#strength h3{color:#136b3e} #dev h3{color:#b4372d}
#strengthBody,#devBody{font-family:"Cairo", Tahoma, sans-serif;font-size:11.2px;line-height:1.45}

/* أزرار */
.actions{display:flex;gap:6px;justify-content:center;margin:8px 0 4px}
.btn{padding:7px 10px;border-radius:10px;border:1px solid #cfe1dd;background:#eaf3f1;color:#09312d;font-weight:700;font-size:12.5px}
.btn.primary{background:#0f7a66;color:#fff;border-color:#0f7a66}
.btn.dark{background:#0f4c46;color:#fff;border-color:#0f4c46}
.btn.whatsapp{display:inline-flex;align-items:center;gap:6px;background:#c9f8dc;color:#065f46;border-color:#22c55e}
.btn svg{width:16px;height:16px}

/* تلوين قيم الدرجات */
select.grade[data-g="5"]{background:#eaf8f1}
select.grade[data-g="4"]{background:#f3faea}
select.grade[data-g="3"]{background:#fff8e8}
select.grade[data-g="2"]{background:#fff0e6}
select.grade[data-g="1"]{background:#ffe8e6}

/* حقوق */
.footer{margin:6px 0 2px;text-align:center;font-size:10.3px;color:#6a8682}
.footer:before{content:"© ";}

/* طباعة صفحة واحدة */
@page{size:A4 portrait; margin:4mm 5mm 5mm 5mm}
@media print{
  html,body{height:auto;margin:0!important;padding:0!important}
  #page{width:210mm;min-height:297mm}
  .wrap{max-width:100%;padding:4mm 5mm}
  table{font-size:10.1px}
  td.brief{font-size:10.1px;line-height:1.35}
  th,td{padding:3.5px 5px}
  .card{min-height:44px}
  .no-print{display:none!important}
}

/* طبقة التحجيم (للحفظ فقط) */
#sheet{transform-origin:top center}
</style>
</head>
<body>
<div id="page">
  <div class="wrap" id="sheet">

    <!-- الهيدر -->
    <header>
      <div class="topline">الإدارة العامة للتعليم بالمنطقة الشرقية • قطاع التعليم بالخبر • مدرسة اليعقوبي الثانوية</div>
      <div class="schooltitle">
        <h1>تقييم الأداء الوظيفي للمعلمين للعام ١٤٤٧هـ</h1>
        <span class="badge" id="hijriChip">التاريخ الهجري: —</span>
      </div>
    </header>

    <!-- تعريف مختصر -->
    <div class="note">
      هذا نموذج قبلي موجّه للمعلم للتعرّف إلى عناصر التقييم وآلية احتسابها. اختر درجة (١–٥) لكل عنصر اعتمادًا على التفسير المختصر المقابل؛ وسيُحتسب <b>مؤشر الإنجاز</b> وتُصاغ <b>نقاط القوة</b> و<b>مجالات التطوير</b> تلقائيًا بصياغات تربوية موجزة. الطباعة/الحفظ تخرج في صفحة A4 واحدة ملونة.
    </div>

    <!-- قائمة المعلمين -->
    <div class="teacher-row">
      <div class="f">
        <label>قائمة المعلمين (اختر ليتم تعبئة البيانات تلقائيًا)</label>
        <select id="tSelect">
          <option value="">— اختر من القائمة —</option>
        </select>
      </div>
    </div>

    <!-- بيانات -->
    <div class="info-row">
      <div class="f"><label>اسم المعلم</label><input id="tName" placeholder="أدخل الاسم ثلاثيًا"/></div>
      <div class="f"><label>رقم الهوية</label><input id="tId" placeholder="10 أرقام"/></div>
      <div class="f"><label>التخصص</label><input id="tSpec" placeholder="مثال: فيزياء"/></div>
      <div class="f"><label>مرحلة التقييم</label>
        <select id="tStage" class="mini-select">
          <option value="الأولى" selected>الأولى</option>
          <option value="الثانية">الثانية</option>
          <option value="الثالثة">الثالثة</option>
        </select>
      </div>
    </div>

    <!-- المؤشر -->
    <div class="bar-row">
      <div class="chip" id="scoreChip">مؤشر الإنجاز: 0.00 / 5</div>
      <div class="meter"><div class="fill"></div><div class="thumb" id="thumb" style="left:100%"></div></div>
      <div class="chip" id="percentChip">المجموع: %0</div>
    </div>
    <div class="scale"><span class="t5">5</span><span class="t4">4</span><span class="t3">3</span><span class="t2">2</span><span class="t1">1</span></div>

    <!-- الجدول -->
    <table id="tbl">
      <thead>
        <tr>
          <th class="w-tight">#</th>
          <th>العنصر</th>
          <th class="w">الوزن</th>
          <th class="w-tight">الدرجة<span class="sub">(1–5)</span></th>
          <th>تفسير / أمثلة مختصرة</th>
        </tr>
      </thead>
      <tbody id="rows"></tbody>
    </table>

    <!-- القوة/التطوير -->
    <div class="cards">
      <div id="strength" class="card">
        <h3>نقاط القوة</h3>
        <div id="strengthBody">—</div>
      </div>
      <div id="dev" class="card">
        <h3>مجالات التطوير</h3>
        <div id="devBody">—</div>
      </div>
    </div>

    <!-- أزرار -->
    <div class="actions no-print">
      <button class="btn" onclick="if(validate())doPrint()">طباعة A4</button>
      <button class="btn primary" id="saveBtn" onclick="if(validate())savePDF()">حفظ PDF</button>
      <button class="btn whatsapp" title="إرسال واتساب" onclick="if(validate())sendWhatsApp()">
        <!-- أيقونة واتساب -->
        <svg viewBox="0 0 32 32" aria-hidden="true"><path fill="#25D366" d="M19.11 17.4c-.27-.13-1.58-.77-1.83-.85-.25-.09-.43-.13-.62.13-.18.27-.71.85-.87 1.02-.16.18-.32.2-.59.07-.27-.13-1.12-.41-2.13-1.31-.79-.71-1.33-1.58-1.48-1.85-.16-.27-.02-.41.11-.54.12-.12.27-.32.41-.48.14-.16.18-.27.27-.45.09-.18.05-.34-.02-.48-.07-.13-.62-1.49-.85-2.05-.22-.54-.45-.46-.62-.46h-.53c-.18 0-.48.07-.73.34-.25.27-.96.94-.96 2.29s.98 2.66 1.12 2.85c.14.18 1.93 2.95 4.69 4.14.66.29 1.18.46 1.58.59.66.21 1.25.18 1.72.11.53-.08 1.58-.65 1.81-1.28.23-.63.23-1.16.16-1.28-.06-.11-.23-.18-.5-.31z"/><path fill="#128C7E" d="M16.03 3.2C9.97 3.2 5.06 8.1 5.06 14.17c0 2.42.79 4.66 2.11 6.47L6.2 27.2l6.73-1.76c1.73.95 3.71 1.49 5.82 1.49 6.06 0 10.97-4.9 10.97-10.97S22.09 3.2 16.03 3.2zm0 19.95c-1.9 0-3.66-.57-5.13-1.54l-3.57.93.95-3.48c-1.07-1.56-1.69-3.44-1.69-5.46 0-5.43 4.41-9.84 9.84-9.84s9.84 4.41 9.84 9.84-4.41 9.85-9.84 9.85z"/></svg>
        إرسال واتساب
      </button>
    </div>

    <!-- حقوق -->
    <div class="footer">إعداد وتنفيذ وتصميم: فهد حامد الزهراني</div>
  </div>
</div>

<script>
/* ===== التاريخ الهجري (أم القرى) ===== */
function hijriUmmAlQura(){
  let txt='—';
  try{
    const opt={weekday:'long',day:'numeric',month:'long',year:'numeric'};
    txt=new Intl.DateTimeFormat('ar-SA-u-ca-islamic-umalqura',opt).format(new Date());
  }catch(e){
    try{ txt=new Intl.DateTimeFormat('ar-SA-u-ca-islamic',{weekday:'long',day:'numeric',month:'long',year:'numeric'}).format(new Date()); }
    catch{ txt=new Date().toLocaleDateString('ar-SA'); }
  }
  document.getElementById('hijriChip').textContent='التاريخ الهجري: '+txt+' هـ';
  return txt+' هـ';
}
const hijriToday=hijriUmmAlQura();

/* ===== بيانات المعلمين (من ملفّك) ===== */
const teachers=[
  {name:"موسى صلبان عبده عسيري",id:"1093013116",spec:"فيزياء"},
  {name:"مبارك عوضه سفر آل ثابت",id:"1056464405",spec:"كيمياء"},
  {name:"فرج عبدالعلي يوسف ال سيف",id:"1000397735",spec:"احياء"},
  {name:"منذر عامر حمود زميع",id:"1065913053",spec:"انجليزي"},
  {name:"سامي عبيد عبدالله العرابي",id:"1020850549",spec:"عربي"},
  {name:"عماد محمد جمعان الزهراني",id:"1048667289",spec:"مكتبات"},
  {name:"ابراهيم حبيب عبدالغني الميمني",id:"1072815481",spec:"رياضيات"},
  {name:"بندر عبدالعزيز محمد الغامدي",id:"1046853881",spec:"حاسب"},
  {name:"حسين بن محمد بن فهد ال قريش القحطاني",id:"1014268567",spec:"احياء"},
  {name:"ناصر علي ناصر الراشد",id:"1008303370",spec:"حاسب"},
  {name:"حسين بن محمد بن حسين الأحمد",id:"1060369202",spec:"عربي"},
  {name:"عبدالرحمن محمد فرحان القرني",id:"1053065189",spec:"حاسب"},
  {name:"علي سعد سعيد الاصلعي الاحمري",id:"1023999780",spec:"احياء"},
  {name:"محمد حمد عبدالرحمن التويجري",id:"1064745944",spec:"عربي"},
  {name:"عبدالله فيصل بن فطيس الهذلي",id:"1094733290",spec:"رياضيات"},
  {name:"احمد عبدالرحيم عبدالحميد ابوعصيده",id:"1033584234",spec:"انجليزي"},
  {name:"عبدالله بن عبدالعزيز بن سيف السهلي",id:"1063175010",spec:"علم اجتماع"},
  {name:"بشير بن أحمد بن عبدالله آل سليم",id:"1019783917",spec:"مكتبات"},
  {name:"ابراهيم بن محمد بن ابراهيم الربيع",id:"1004182687",spec:"انجليزي"},
  {name:"عبدالمجيد عبدالله سالم آل حبشان",id:"1004581359",spec:"اجتماعيات"},
  {name:"فيصل فهد علي الزهراني",id:"1086115373",spec:"رياضيات"},
  {name:"خالد حسن مانع الشهري",id:"1021900764",spec:"عربي"},
  {name:"عيسى بن خالد بن عبد الرحمن المذن",id:"1072990581",spec:"كيمياء"},
  {name:"زياد عواض ابن عيضه العمري",id:"1092156742",spec:"علم الإدارة"},
  {name:"عبدالرحمن عبدالجبار حمود العتيبي",id:"1089635724",spec:"فيزياء"},
  {name:"عبد الله حسن عمر الادريسي",id:"1081556910",spec:"رياضيات"},
  {name:"تقي عبد الهادي تقي العلي",id:"1026472363",spec:"كيمياء"},
  {name:"صالح بن محمد بن صالح السميحي",id:"1003535422",spec:"دين"},
  {name:"زاهر عبدالله سعد الشهراني",id:"1074173517",spec:"دين"},
  {name:"عادل بن علي بن ناصر البارقي",id:"1007370701",spec:"رياضه"},
  {name:"ابراهيم بن أحمد بن ابراهيم العجلان",id:"1001082179",spec:"دين"},
  {name:"خالد أحمد محمد الشهري",id:"1034318301",spec:"كيمياء"},
  {name:"خالد سعد راشد المرضي",id:"1025640010",spec:"اجتماعيات"},
  {name:"عبدالله بن خلوفة بن عبدالله ال مرعي",id:"1029490875",spec:"دين"},
  {name:"يحيى بن محمد بن سعيد القحطاني",id:"1048978892",spec:"اجتماعيات"},
  {name:"حسين بن سعيد سلمان المدن",id:"1022616799",spec:"مكتبات"},
  {name:"يوسف عيسى عيسى العيد",id:"1012646822",spec:"عربي"},
  {name:"نبيل بن محسن محمد القلاف",id:"1025472604",spec:"رياضه"},
  {name:"عبدالمجيد عبدالرحمن عبدالله السالمي",id:"1073861831",spec:"انجليزي"},
  {name:"حسن علي حسن الشهري",id:"1037273594",spec:"عربي"},
  {name:"جميل عبدالمجيد جواد العلي",id:"1029281589",spec:"فيزياء"},
  {name:"عبد الهادي محمد حبيب العايش",id:"1058489277",spec:"رياضيات"},
  {name:"حسن يوسف حسين الخليفة",id:"1056994203",spec:"كيمياء"},
  {name:"حسن عبدالله علي العبدالله",id:"1005472780",spec:"احياء"}
];

/* تعبئة القائمة المنسدلة بالمعلمين */
const tSelect=document.getElementById('tSelect');
teachers.forEach((t,i)=>{
  const op=document.createElement('option');
  op.value=String(i);
  op.textContent=t.name; // عرض الاسم كاملاً
  tSelect.appendChild(op);
});
tSelect.addEventListener('change',()=>{
  if(tSelect.value==="") return;
  const t=teachers[Number(tSelect.value)];
  document.getElementById('tName').value=t.name;
  document.getElementById('tId').value=t.id;
  document.getElementById('tSpec').value=t.spec;
});

/* ===== عناصر التقييم ===== */
const items=[
  {name:"أداء الواجبات الوظيفية",weight:10,brief:"انضباط يومي؛ التزام بالجدول والمواعيد؛ تحضير وتتبع للدرس؛ تسليم التقارير في وقتها."},
  {name:"التفاعل مع المجتمع المهني",weight:10,brief:"مجتمعات تعلم مهنية؛ تبادل زيارات؛ حضور دورات؛ مشاركة موارد وخبرات."},
  {name:"التفاعل مع أولياء الأمور",weight:10,brief:"قنوات تواصل منضبطة؛ رسائل موجزة؛ متابعة بنّاءة لحالات الطلاب."},
  {name:"التنوع في استراتيجيات التدريس",weight:10,brief:"تنويع أساليب التعلم النشط؛ مراعاة الفروق؛ أسئلة عليا؛ تعلم تعاوني."},
  {name:"تحسين نتائج المتعلمين",weight:10,brief:"قياس قبلي/بعدي؛ خطط علاج للفاقد؛ إثراء للمتفوقين؛ متابعة تقدم."},
  {name:"إعداد وتنفيذ خطة التعلم",weight:10,brief:"توزيع منهج معتمد؛ تحضير علمي؛ تقويم بنائي؛ تنفيذ ملتزم بالزمن."},
  {name:"توظيف تقنيات ووسائل التعلم المناسبة",weight:10,brief:"منصات تعليم؛ موارد تفاعلية؛ مصادر متعددة؛ محتوى منظم ومناسب."},
  {name:"تهيئة البيئة التعليمية",weight:5, brief:"تهيئة نفسية محفّزة؛ تنظيم المقاعد؛ لوحات وإرشادات صفية."},
  {name:"الإدارة الصفية",weight:5,  brief:"قواعد وضوابط واضحة؛ إدارة وقت دقيقة؛ انتقالات سلسة؛ متابعة الغياب."},
  {name:"تحليل نتائج المتعلمين وتشخيص مستوياتهم",weight:10,brief:"تحليل بنود الاختبار؛ تحديد نقاط القوة والضعف؛ تقارير مختصرة."},
  {name:"تنوع أساليب التقويم",weight:10,brief:"اختبارات تحريرية/شفهية/عملية/إلكترونية؛ مهام أداء؛ ملفات إنجاز."},
];
const strengthPhrases={
 "أداء الواجبات الوظيفية":"انضباط وظيفي والتزام بالمواعيد وجودة متابعة للتحضير والتقارير.",
 "التفاعل مع المجتمع المهني":"حضور فاعل وتبادل خبرات يثري الممارسة الصفية.",
 "التفاعل مع أولياء الأمور":"تواصل راقٍ وموجّه يسهم في دعم تعلم الأبناء.",
 "التنوع في استراتيجيات التدريس":"تنويع مؤثر يحقق مشاركة وفاعلية المتعلمين.",
 "تحسين نتائج المتعلمين":"خطط علاج وإثراء انعكست على نتائج الطلاب.",
 "إعداد وتنفيذ خطة التعلم":"تنفيذ محكم لخطة تعليمية متوازنة وتقويم بنائي.",
 "توظيف تقنيات ووسائل التعلم المناسبة":"اختيار أدوات مناسبة تُحفّز التفاعل وتثري المحتوى.",
 "تهيئة البيئة التعليمية":"بيئة آمنة ومحفّزة تُظهر أثرًا إيجابيًا على المشاركة.",
 "الإدارة الصفية":"انضباط واضح وتنظيم وقت فعّال وانتقالات سلسة.",
 "تحليل نتائج المتعلمين وتشخيص مستوياتهم":"تحليل دقيق للنتائج وتوجيه بنّاء لتحسين الأداء.",
 "تنوع أساليب التقويم":"تقويم متنوع يقيس التعلم ويغذّيه راجعًا."
};
const devPhrases={
 "أداء الواجبات الوظيفية":"تعزيز توثيق التحضير وضبط المواعيد وتفعيل المتابعة الأسبوعية.",
 "التفاعل مع المجتمع المهني":"زيادة المبادرات المهنية وتبادل الزيارات والتجارب الصفية.",
 "التفاعل مع أولياء الأمور":"تنويع قنوات التواصل وجدولتها برسائل موجزة وواضحة.",
 "التنوع في استراتيجيات التدريس":"توسيع التنويع وتفعيل أنشطة تعلم نشط تراعي الفروق.",
 "تحسين نتائج المتعلمين":"تطوير خطط علاجية دقيقة وربطها بمؤشرات تقدم أسبوعية.",
 "إعداد وتنفيذ خطة التعلم":"مراجعة التحضير العلمي وربط الأهداف بمعايير قياس واضحة.",
 "توظيف تقنيات ووسائل التعلم المناسبة":"إثراء المحتوى بأدوات رقمية تفاعلية مناسبة للدرس.",
 "تهيئة البيئة التعليمية":"تحسين التهيئة النفسية وتنظيم المقاعد بما يدعم التفاعل.",
 "الإدارة الصفية":"تثبيت قواعد صفية واضحة وتحسين إدارة الوقت والانتقال.",
 "تحليل نتائج المتعلمين وتشخيص مستوياتهم":"توسيع تحليل البنود وبناء ملفات تقدم مختصرة.",
 "تنوع أساليب التقويم":"تفعيل التقويم العملي والشفهي والإلكتروني بشكل أوسع."
};

/* بناء الجدول */
const tbody=document.getElementById('rows');
items.forEach((it,idx)=>{
  const tr=document.createElement('tr');
  tr.innerHTML=`
    <td class="w-tight" style="text-align:center">${idx+1}</td>
    <td>${it.name}</td>
    <td class="w"><b>${it.weight}%</b></td>
    <td class="w-tight">
      <select class="grade" data-g="3" aria-label="درجة العنصر">
        <option value="5">5</option><option value="4">4</option>
        <option value="3" selected>3</option><option value="2">2</option><option value="1">1</option>
      </select>
    </td>
    <td class="brief">${it.brief}</td>`;
  tbody.appendChild(tr);
});

/* ديناميكيات الحساب */
const gradesEls=[...document.querySelectorAll('.grade')];
const percentChip=document.getElementById('percentChip');
const scoreChip=document.getElementById('scoreChip');
const thumb=document.getElementById('thumb');
const strengthBody=document.getElementById('strengthBody');
const devBody=document.getElementById('devBody');

function overallText(avg){
  if(avg>=4.5) return "مثالي";
  if(avg>=3.5) return "تخطّى التوقعات";
  if(avg>=2.5) return "وافق التوقعات";
  if(avg>=1.5) return "بحاجة إلى تطوير";
  return "غير مرضي";
}

function recalc(){
  let weighted=0, per=0, strengths=[], devs=[];
  gradesEls.forEach((sel,i)=>{
    const g=Number(sel.value); sel.dataset.g=g;
    const w=items[i].weight;
    weighted += g*w;
    per += (g/5)*w;
    const name=items[i].name;
    if(g>=4) strengths.push(`• ${strengthPhrases[name]}`);
    if(g<=3) devs.push(`• ${devPhrases[name]}`);
  });
  const avg=weighted/100; const pct=Math.round(per);
  scoreChip.textContent=`مؤشر الإنجاز: ${avg.toFixed(2)} / 5`;
  percentChip.textContent=`المجموع: %${pct}`;
  const pos=((5-avg)/4)*100; thumb.style.left=`${pos}%`;
  let bcol='#33524e'; if(avg>=4.5) bcol='#1c7f4d'; else if(avg<=2) bcol='#b32828'; else bcol='#a86a19';
  thumb.style.borderColor=bcol;
  strengthBody.innerHTML=strengths.length?strengths.join('<br>'):'—';
  devBody.innerHTML=devs.length?devs.join('<br>'):'—';
  return {avg,pct,overall:overallText(avg)};
}
gradesEls.forEach(el=>el.addEventListener('change',recalc));
recalc();

/* ضغط للحفظ كصفحة واحدة */
const SHEET=document.getElementById('sheet');
function fitOnce(){
  const mmToPx=3.78, avail=(297-14)*mmToPx;
  const h=SHEET.scrollHeight, scale=Math.min(1,(avail/h)*0.995);
  SHEET.dataset.prev=SHEET.style.transform||'';
  SHEET.style.transform=`scale(${scale})`;
  return scale;
}
function unfit(){ if(SHEET.dataset.prev!==undefined){SHEET.style.transform=SHEET.dataset.prev; delete SHEET.dataset.prev;} }

/* تحقق قبل الإجراءات */
function validate(){
  const name=document.getElementById('tName').value.trim();
  const id=document.getElementById('tId').value.trim();
  const spec=document.getElementById('tSpec').value.trim();
  if(!name){ alert('رجاءً اختر المعلم من القائمة أو اكتب اسمه.'); document.getElementById('tName').focus(); return false; }
  if(!/^\d{10}$/.test(id)){ alert('رجاءً أدخل رقم هوية صحيحًا (10 أرقام).'); document.getElementById('tId').focus(); return false; }
  if(!spec){ alert('رجاءً اكتب التخصص.'); document.getElementById('tSpec').focus(); return false; }
  if(gradesEls.some(s=>!s.value)){ alert('رجاءً إنهاء درجات جميع العناصر.'); return false; }
  return true;
}

/* طباعة */
function doPrint(){ fitOnce(); setTimeout(()=>window.print(),60); }
window.addEventListener('afterprint',unfit);

/* حفظ PDF */
async function savePDF(){
  try{
    document.getElementById('saveBtn').disabled=true;
    const name=(document.getElementById('tName').value||'غير_مسمى').replace(/\s+/g,' ');
    const stage=document.getElementById('tStage').value;
    const filename=`تقييم الأداء الوظيفي - ${name} - مرحلة ${stage} - ${hijriToday}.pdf`;

    fitOnce();
    await new Promise(r=>setTimeout(r,120));

    const node=document.getElementById('page');
    const canvas=await html2canvas(node,{useCORS:true,scale:2,background:'#ffffff',scrollX:0,scrollY:0});
    const imgData=canvas.toDataURL('image/png',1.0);
    const {jsPDF}=window.jspdf;
    const pdf=new jsPDF({unit:'mm',format:'a4',orientation:'portrait'});

    const margin=5;
    const pdfW=210-2*margin, pdfH=297-2*margin;
    const imgWmm=canvas.width*0.264583, imgHmm=canvas.height*0.264583;
    const ratio=Math.min(pdfW/imgWmm, pdfH/imgHmm);
    const w=imgWmm*ratio, h=imgHmm*ratio;
    const x=margin+(pdfW-w)/2, y=margin+(pdfH-h)/2;

    pdf.addImage(imgData,'PNG',x,y,w,h,'','FAST');
    pdf.save(filename);
  }catch(err){
    alert('تعذّر الحفظ PDF. جرّب من جديد.'); console.error(err);
  }finally{
    unfit(); document.getElementById('saveBtn').disabled=false;
  }
}

/* واتساب — ملخّص مختصر فقط */
function sendWhatsApp(){
  const phone='966504532489';
  const name=document.getElementById('tName').value.trim();
  const stage=document.getElementById('tStage').value;
  const S=recalc();
  const msg =
`السلام عليكم،
ملخص قبلي من المعلم بمدرسة اليعقوبي الثانوية:
الاسم: ${name}
مرحلة التقييم: ${stage}
${document.getElementById('scoreChip').textContent} | ${document.getElementById('percentChip').textContent}
التقدير العام: ${S.overall}
(سيتم لاحقًا إرسال ملف PDF الكامل إلى المدير.)
التاريخ الهجري: ${hijriToday}`;
  const encoded=encodeURIComponent(msg);

  // المسار الأساسي + فول-باك
  let url=`https://api.whatsapp.com/send?phone=${phone}&text=${encoded}`;
  let win=window.open(url,'_blank');
  setTimeout(()=>{ if(!win || win.closed || typeof win.closed==='undefined'){ window.location.href=`https://wa.me/${phone}?text=${encoded}`; }}, 400);
}

/* تهيئة التاريخ */
(function initHijri(){ hijriUmmAlQura(); })();

/* تحسين للجوال */
(function mobileTune(){
  if(window.innerWidth<640){ document.documentElement.style.fontSize='14px'; }
})();
</script>
</body>
</html>
