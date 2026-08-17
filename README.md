<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>التقرير اليومي — موقع العمل</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@500;700;800;900&family=Tajawal:wght@400;500;700&family=IBM+Plex+Mono:wght@500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#17242E;
    --ink-soft:#3F5160;
    --steel:#5C6B73;
    --paper:#F6F4EE;
    --paper-line:#E4E0D4;
    --card:#FFFFFF;
    --navy:#1B3A4B;
    --navy-deep:#122733;
    --safety:#E2611E;
    --safety-soft:#FBE4D3;
    --ok:#3E7C59;
    --ok-soft:#DEEBE2;
    --warn:#C0392B;
    --warn-soft:#F6DEDA;
    --radius:10px;
  }
  *{box-sizing:border-box;}
  body{
    margin:0;
    background:
      linear-gradient(var(--paper-line) 1px, transparent 1px) 0 0/100% 34px,
      var(--paper);
    color:var(--ink);
    font-family:'Tajawal', sans-serif;
    padding:28px 14px 80px;
  }
  .sheet{
    max-width:1180px;
    margin:0 auto;
  }

  /* ===== TITLE BLOCK ===== */
  .titleblock{
    background:var(--navy-deep);
    background-image:
      repeating-linear-gradient(90deg, rgba(255,255,255,0.035) 0 1px, transparent 1px 40px),
      repeating-linear-gradient(0deg, rgba(255,255,255,0.035) 0 1px, transparent 1px 40px);
    border-radius:var(--radius);
    padding:26px 28px 22px;
    color:#EDEFEF;
    position:relative;
    overflow:hidden;
    border:1px solid var(--navy-deep);
  }
  .titleblock::before{
    content:"";
    position:absolute; inset:8px;
    border:1px solid rgba(255,255,255,0.18);
    border-radius:6px;
    pointer-events:none;
  }
  .tb-top{
    display:flex; justify-content:space-between; align-items:flex-start; gap:18px;
    flex-wrap:wrap;
    margin-bottom:18px;
  }
  .tb-brand{display:flex; align-items:center; gap:12px;}
  .tb-mark{
    width:44px;height:44px;border-radius:8px;
    background:var(--safety);
    display:flex;align-items:center;justify-content:center;
    font-family:'Cairo';font-weight:900;font-size:20px;color:#1a1a1a;
    flex:none;
  }
  .tb-brand input{
    background:transparent;border:none;color:#fff;
    font-family:'Cairo';font-weight:800;font-size:20px;
    padding:2px 4px; width:260px; border-bottom:1px dashed rgba(255,255,255,0.3);
  }
  .tb-sub{font-size:11px;letter-spacing:1.5px;color:#9FB0B9;font-family:'IBM Plex Mono';text-transform:uppercase;margin-top:4px;}
  .tb-report-tag{
    text-align:left;
    font-family:'IBM Plex Mono';
  }
  .tb-report-tag .rlabel{font-size:10px;color:#9FB0B9;letter-spacing:2px;text-transform:uppercase;}
  .tb-report-tag input[type=date]{
    background:var(--safety);color:#1a1a1a;border:none;border-radius:5px;
    padding:6px 10px;font-family:'IBM Plex Mono';font-weight:600;font-size:14px;margin-top:3px;
  }
  .tb-grid{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:0;
    border-top:1px solid rgba(255,255,255,0.18);
  }
  .tb-cell{
    padding:12px 16px;
    border-left:1px solid rgba(255,255,255,0.18);
  }
  .tb-cell:last-child{border-left:none;}
  .tb-cell label{
    display:block;font-size:10.5px;color:#9FB0B9;letter-spacing:1px;
    font-family:'IBM Plex Mono';text-transform:uppercase;margin-bottom:5px;
  }
  .tb-cell input, .tb-cell select{
    width:100%;background:transparent;border:none;color:#fff;
    font-family:'Tajawal';font-weight:500;font-size:14.5px;
    border-bottom:1px solid rgba(255,255,255,0.25);padding-bottom:4px;
  }
  .tb-cell input::placeholder{color:#77878F;}
  .tb-cell select option{color:#111;}
  .weather-row{display:flex;gap:8px;align-items:center;}
  .weather-row input{width:70px;}
  .weather-row span{color:#9FB0B9;font-size:12px;}

  /* ===== SECTIONS ===== */
  .section{
    background:var(--card);
    border:1px solid var(--paper-line);
    border-radius:var(--radius);
    margin-top:18px;
    overflow:hidden;
  }
  .section-head{
    display:flex;align-items:center;gap:12px;
    padding:16px 20px;
    border-bottom:1px solid var(--paper-line);
    background:linear-gradient(180deg,#FCFBF8,#F6F4EE);
  }
  .section-num{
    font-family:'IBM Plex Mono';font-weight:600;font-size:12px;
    color:var(--safety); border:1px solid var(--safety);
    border-radius:5px; padding:3px 8px; flex:none;
  }
  .section-head h2{
    font-family:'Cairo';font-weight:800;font-size:17px;margin:0;color:var(--navy-deep);
  }
  .section-head p{margin:2px 0 0;font-size:12px;color:var(--steel);}
  .section-body{padding:18px 20px 22px;}

  /* ===== TABLES ===== */
  table{width:100%;border-collapse:collapse;font-size:13.5px;}
  thead th{
    background:var(--navy);color:#EDEFEF;
    font-family:'Cairo';font-weight:700;font-size:12.5px;
    padding:10px 8px;text-align:right;white-space:nowrap;
  }
  tbody td{
    border-bottom:1px solid var(--paper-line);
    padding:6px 7px;vertical-align:middle;
  }
  tbody tr:hover{background:#FBFAF6;}
  td input, td select, textarea{
    width:100%;border:1px solid #E1DDD0;border-radius:6px;
    padding:7px 8px;font-family:'Tajawal';font-size:13px;background:#fff;color:var(--ink);
  }
  td input:focus, td select:focus, textarea:focus, .tb-cell input:focus{outline:2px solid var(--safety);outline-offset:1px;}
  .num-cell input{text-align:center;}
  .del-btn{
    background:var(--warn-soft);color:var(--warn);border:none;border-radius:6px;
    width:30px;height:30px;cursor:pointer;font-size:15px;font-weight:700;
  }
  .del-btn:hover{background:var(--warn);color:#fff;}
  .add-row-btn{
    margin-top:10px;
    background:var(--navy);color:#fff;border:none;border-radius:7px;
    padding:9px 16px;font-family:'Cairo';font-weight:700;font-size:13px;cursor:pointer;
    display:inline-flex;align-items:center;gap:6px;
  }
  .add-row-btn:hover{background:var(--navy-deep);}
  .table-wrap{overflow-x:auto;}
  tfoot td{
    font-family:'Cairo';font-weight:800;background:var(--safety-soft);color:var(--navy-deep);
    padding:9px 8px;
  }

  /* ===== TWO COL GRID ===== */
  .two-col{display:grid;grid-template-columns:1fr 1fr;gap:18px;}
  @media(max-width:800px){.two-col{grid-template-columns:1fr;} .tb-grid{grid-template-columns:1fr 1fr;} .titleblock{padding:20px;}}

  .subcard{
    border:1px solid var(--paper-line);border-radius:8px;padding:14px;background:#FCFBF8;
  }
  .subcard h3{
    font-family:'Cairo';font-size:14px;margin:0 0 8px;color:var(--navy);
    display:flex;align-items:center;gap:6px;
  }
  .subcard textarea{min-height:80px;resize:vertical;margin-bottom:10px;}
  .check-list{display:flex;flex-direction:column;gap:8px;margin-bottom:10px;}
  .check-list label{display:flex;align-items:center;gap:8px;font-size:13px;color:var(--ink-soft);cursor:pointer;}
  .check-list input[type=checkbox]{width:17px;height:17px;accent-color:var(--safety);}

  /* ===== PHOTOS ===== */
  .photo-upload-zone{
    border:2px dashed #CBC5B4;border-radius:9px;padding:22px;text-align:center;
    color:var(--steel);font-size:13px;cursor:pointer;transition:.15s;background:#FCFBF8;
  }
  .photo-upload-zone:hover{border-color:var(--safety);color:var(--safety);background:var(--safety-soft);}
  .photo-upload-zone input{display:none;}
  .photo-grid{
    display:grid;grid-template-columns:repeat(auto-fill,minmax(190px,1fr));
    gap:14px;margin-top:14px;
  }
  .photo-card{
    border:1px solid var(--paper-line);border-radius:8px;overflow:hidden;background:#fff;
    position:relative;
  }
  .photo-card img{width:100%;height:130px;object-fit:cover;display:block;background:#eee;}
  .photo-card .photo-body{padding:8px;}
  .photo-card select{margin-bottom:6px;font-size:12px;padding:5px 6px;}
  .photo-card input{font-size:12px;padding:6px 7px;}
  .photo-card .del-btn{
    position:absolute;top:6px;left:6px;width:26px;height:26px;font-size:13px;
    background:rgba(23,36,46,0.65);color:#fff;
  }
  .photo-empty{font-size:12px;color:var(--steel);text-align:center;padding:10px;}

  /* ===== SIGNATURES ===== */
  .sig-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;}
  @media(max-width:800px){.sig-grid{grid-template-columns:1fr;}}
  .sig-card{border:1px solid var(--paper-line);border-radius:8px;padding:14px;text-align:center;background:#FCFBF8;}
  .sig-card h4{font-family:'Cairo';font-size:13.5px;margin:0 0 3px;color:var(--navy-deep);}
  .sig-card .role-tag{font-size:11px;color:var(--safety);font-family:'IBM Plex Mono';margin-bottom:10px;display:block;}
  .sig-card input[type=text]{margin-bottom:10px;text-align:center;}
  canvas{
    width:100%;height:120px;background:#fff;border:1px solid #E1DDD0;border-radius:6px;
    touch-action:none; cursor:crosshair;
  }
  .sig-actions{display:flex;justify-content:space-between;margin-top:8px;font-size:11px;color:var(--steel);}
  .sig-actions button{
    background:none;border:none;color:var(--warn);font-family:'Tajawal';font-size:12px;cursor:pointer;text-decoration:underline;
  }
  .sig-date{font-family:'IBM Plex Mono';font-size:11px;color:var(--steel);margin-top:6px;}

  /* ===== FOOTER TOOLBAR ===== */
  .toolbar{
    position:sticky;bottom:0;
    display:flex;justify-content:center;gap:12px;
    margin-top:22px;padding:14px;
  }
  .btn-print{
    background:var(--safety);color:#fff;border:none;border-radius:8px;
    padding:13px 30px;font-family:'Cairo';font-weight:800;font-size:14.5px;cursor:pointer;
    box-shadow:0 6px 18px rgba(226,97,30,0.35);
  }
  .btn-print:hover{background:#C6520F;}

  @media print{
    body{background:#fff;padding:0;}
    .toolbar, .add-row-btn, .del-btn, .photo-upload-zone{display:none !important;}
    .section{break-inside:avoid;box-shadow:none;}
    canvas{border:1px solid #999;}
  }
</style>
</head>
<body>
<div class="sheet">

  <!-- ===== TITLE BLOCK ===== -->
  <div class="titleblock">
    <div class="tb-top">
      <div class="tb-brand">
        <div class="tb-mark">⚒</div>
        <div>
          <input type="text" id="companyName" value="شركة الإتقان للمقاولات والإشراف الهندسي">
          <div class="tb-sub">Daily Site Report · تقرير الموقع اليومي</div>
        </div>
      </div>
      <div class="tb-report-tag">
        <span class="rlabel">تاريخ التقرير</span>
        <input type="date" id="reportDate">
      </div>
    </div>
    <div class="tb-grid">
      <div class="tb-cell">
        <label>اسم المشروع</label>
        <input type="text" id="projectName" placeholder="مثال: برج السلام السكني">
      </div>
      <div class="tb-cell">
        <label>المقاول الرئيسي</label>
        <input type="text" id="contractorName" placeholder="اسم شركة المقاولات">
      </div>
      <div class="tb-cell">
        <label>الاستشاري / المهندس المشرف</label>
        <input type="text" id="consultantName" placeholder="اسم المكتب الاستشاري">
      </div>
      <div class="tb-cell">
        <label>حالة الطقس في الموقع</label>
        <div class="weather-row">
          <input type="number" id="weatherTemp" placeholder="32">
          <span>°م</span>
          <select id="weatherState">
            <option value="مشمس">☀️ مشمس</option>
            <option value="غائم">☁️ غائم</option>
            <option value="غائم جزئياً">⛅ غائم جزئياً</option>
            <option value="ممطر">🌧️ ممطر</option>
            <option value="عاصف">🌬️ عاصف</option>
            <option value="غبار">🌫️ غبار / رمال</option>
          </select>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== 1. LABOR & TECHNICAL CREW ===== -->
  <div class="section">
    <div class="section-head">
      <span class="section-num">01</span>
      <div>
        <h2>سجل العمالة والكوادر الفنية</h2>
        <p>عدد الفنيين والعمالة العاملة في الموقع اليوم حسب التخصص</p>
      </div>
    </div>
    <div class="section-body">
      <div class="table-wrap">
        <table id="laborTable">
          <thead><tr><th style="width:45%">التخصص / المسمى</th><th style="width:20%">العدد</th><th>ملاحظات</th><th style="width:40px"></th></tr></thead>
          <tbody></tbody>
          <tfoot><tr><td>الإجمالي</td><td class="num-cell" id="laborTotal">0</td><td colspan="2"></td></tr></tfoot>
        </table>
      </div>
      <button class="add-row-btn" onclick="addLaborRow()">+ إضافة تخصص</button>
    </div>
  </div>

  <!-- ===== 2. ATTENDANCE ===== -->
  <div class="section">
    <div class="section-head">
      <span class="section-num">02</span>
      <div>
        <h2>سجل الحضور والغياب</h2>
        <p>حضور وانصراف الموظفين، المشرفين، والمشغلين</p>
      </div>
    </div>
    <div class="section-body">
      <div class="table-wrap">
        <table id="attendanceTable">
          <thead><tr>
            <th style="width:20%">الاسم</th><th style="width:16%">المسمى الوظيفي</th>
            <th style="width:12%">وقت الحضور</th><th style="width:12%">وقت الانصراف</th>
            <th style="width:13%">الحالة</th><th>ملاحظات</th><th style="width:40px"></th>
          </tr></thead>
          <tbody></tbody>
        </table>
      </div>
      <button class="add-row-btn" onclick="addAttendanceRow()">+ إضافة موظف</button>
    </div>
  </div>

  <!-- ===== 3. DAILY WORKS ===== -->
  <div class="section">
    <div class="section-head">
      <span class="section-num">03</span>
      <div>
        <h2>الأعمال المنجزة اليوم</h2>
        <p>الأنشطة والمهام التي تم تنفيذها خلال يوم العمل</p>
      </div>
    </div>
    <div class="section-body">
      <div class="table-wrap">
        <table id="worksTable">
          <thead><tr><th style="width:22%">البند / النشاط</th><th style="width:38%">الوصف</th><th style="width:14%">نسبة الإنجاز %</th><th>ملاحظات</th><th style="width:40px"></th></tr></thead>
          <tbody></tbody>
        </table>
      </div>
      <button class="add-row-btn" onclick="addWorkRow()">+ إضافة نشاط</button>
    </div>
  </div>

  <!-- ===== 4. MATERIALS & EQUIPMENT ===== -->
  <div class="section">
    <div class="section-head">
      <span class="section-num">04</span>
      <div>
        <h2>المشتونات والمعدات</h2>
        <p>المواد الموردة للموقع، والآليات العاملة والمتوقفة</p>
      </div>
    </div>
    <div class="section-body">
      <h3 style="font-family:'Cairo';font-size:14px;color:var(--navy);margin:0 0 8px;">المواد والمشتونات الموردة</h3>
      <div class="table-wrap">
        <table id="materialsTable">
          <thead><tr><th style="width:28%">المادة</th><th style="width:14%">الكمية</th><th style="width:14%">الوحدة</th><th>المورد / ملاحظات</th><th style="width:40px"></th></tr></thead>
          <tbody></tbody>
        </table>
      </div>
      <button class="add-row-btn" onclick="addMaterialRow()">+ إضافة مادة</button>

      <h3 style="font-family:'Cairo';font-size:14px;color:var(--navy);margin:22px 0 8px;">المعدات والآليات</h3>
      <div class="table-wrap">
        <table id="equipmentTable">
          <thead><tr><th style="width:28%">المعدة / الآلية</th><th style="width:16%">الحالة</th><th style="width:16%">عدد ساعات التشغيل</th><th>ملاحظات</th><th style="width:40px"></th></tr></thead>
          <tbody></tbody>
        </table>
      </div>
      <button class="add-row-btn" onclick="addEquipmentRow()">+ إضافة معدة</button>
    </div>
  </div>

  <!-- ===== 5. ENGINEERING WORKS ===== -->
  <div class="section">
    <div class="section-head">
      <span class="section-num">05</span>
      <div>
        <h2>الأعمال الهندسية والتصاميم</h2>
        <p>مراجعة الأعمال المعمارية والإنشائية ومرفقاتها</p>
      </div>
    </div>
    <div class="section-body">
      <div class="two-col">
        <div class="subcard">
          <h3>🏛️ الأعمال المعمارية</h3>
          <textarea id="archNotes" placeholder="ملاحظات على التصاميم المعمارية، مطابقة التنفيذ للمخططات، التعديلات المطلوبة..."></textarea>
          <div class="photo-upload-zone" onclick="document.getElementById('archUpload').click()">
            📐 اضغط لإرفاق مخططات / معاينات 2D · 3D
            <input type="file" id="archUpload" accept="image/*" multiple onchange="handleUpload(this, 'archGrid')">
          </div>
          <div class="photo-grid" id="archGrid"></div>
        </div>
        <div class="subcard">
          <h3>🏗️ الأعمال الإنشائية</h3>
          <div class="check-list">
            <label><input type="checkbox"> تأكيد صب الخرسانة</label>
            <label><input type="checkbox"> مراجعة أعمال التسليح</label>
            <label><input type="checkbox"> مطابقة المخططات التنفيذية الإنشائية</label>
          </div>
          <textarea id="structNotes" placeholder="ملاحظات إنشائية: نسبة الخلطة، عدد شدات الصب، نتائج فحص التسليح..."></textarea>
          <div class="photo-upload-zone" onclick="document.getElementById('structUpload').click()">
            📐 اضغط لإرفاق مخططات / صور الأعمال الإنشائية
            <input type="file" id="structUpload" accept="image/*" multiple onchange="handleUpload(this, 'structGrid')">
          </div>
          <div class="photo-grid" id="structGrid"></div>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== 6. PHOTO DOCUMENTATION ===== -->
  <div class="section">
    <div class="section-head">
      <span class="section-num">06</span>
      <div>
        <h2>التوثيق الفوتوغرافي للموقع</h2>
        <p>صور الميدان أثناء سير العمل، وقبل وبعد الإنجاز مع الوصف</p>
      </div>
    </div>
    <div class="section-body">
      <div class="photo-upload-zone" onclick="document.getElementById('siteUpload').click()">
        📷 اضغط لإرفاق صور الموقع (يمكن اختيار أكثر من صورة)
        <input type="file" id="siteUpload" accept="image/*" multiple onchange="handleUpload(this, 'siteGrid', true)">
      </div>
      <div class="photo-grid" id="siteGrid"></div>
    </div>
  </div>

  <!-- ===== 7. SAFETY ===== -->
  <div class="section">
    <div class="section-head">
      <span class="section-num">07</span>
      <div>
        <h2>الأمن والسلامة والملاحظات</h2>
        <p>ملاحظات السلامة والصحة المهنية وتوجيهات المهندس المشرف</p>
      </div>
    </div>
    <div class="section-body">
      <div class="two-col">
        <div class="subcard">
          <h3>🦺 ملاحظات السلامة والصحة المهنية</h3>
          <textarea id="safetyNotes" style="min-height:110px" placeholder="مخالفات السلامة، معدات الحماية الشخصية، الحوادث إن وجدت..."></textarea>
        </div>
        <div class="subcard">
          <h3>📋 توجيهات المهندس المشرف</h3>
          <textarea id="engInstructions" style="min-height:110px" placeholder="التوجيهات والملاحظات الصادرة من المهندس المشرف للمقاول..."></textarea>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== 8. SIGNATURES ===== -->
  <div class="section">
    <div class="section-head">
      <span class="section-num">08</span>
      <div>
        <h2>الاعتماد والتوقيعات</h2>
        <p>توقيع الأطراف المسؤولة عن اعتماد التقرير</p>
      </div>
    </div>
    <div class="section-body">
      <div class="sig-grid">
        <div class="sig-card">
          <h4>مهندس الموقع</h4>
          <span class="role-tag">SITE ENGINEER</span>
          <input type="text" placeholder="الاسم">
          <canvas class="sigpad" width="300" height="120"></canvas>
          <div class="sig-actions"><span>التوقيع</span><button onclick="clearSig(this)">مسح</button></div>
          <div class="sig-date" id="dateSig1"></div>
        </div>
        <div class="sig-card">
          <h4>مهندس السلامة</h4>
          <span class="role-tag">SAFETY ENGINEER</span>
          <input type="text" placeholder="الاسم">
          <canvas class="sigpad" width="300" height="120"></canvas>
          <div class="sig-actions"><span>التوقيع</span><button onclick="clearSig(this)">مسح</button></div>
          <div class="sig-date" id="dateSig2"></div>
        </div>
        <div class="sig-card">
          <h4>مدير المشروع</h4>
          <span class="role-tag">PROJECT MANAGER</span>
          <input type="text" placeholder="الاسم">
          <canvas class="sigpad" width="300" height="120"></canvas>
          <div class="sig-actions"><span>التوقيع</span><button onclick="clearSig(this)">مسح</button></div>
          <div class="sig-date" id="dateSig3"></div>
        </div>
      </div>
    </div>
  </div>

  <div class="toolbar">
    <button class="btn-print" onclick="finalizeAndPrint()">🖨️ طباعة / حفظ التقرير PDF</button>
  </div>
</div>

<script>
// ---------- init date ----------
document.getElementById('reportDate').value = new Date().toISOString().slice(0,10);
const today = new Date().toLocaleDateString('ar-EG', {year:'numeric',month:'long',day:'numeric'});
['dateSig1','dateSig2','dateSig3'].forEach(id=>document.getElementById(id).textContent = today);

// ---------- generic row helpers ----------
function makeDelBtn(tr){
  const btn = document.createElement('button');
  btn.className='del-btn'; btn.type='button'; btn.textContent='✕';
  btn.onclick=()=>{ tr.remove(); recalcLaborTotal(); };
  return btn;
}
function cellInput(type='text', value='', placeholder=''){
  const inp=document.createElement('input');
  inp.type=type; inp.value=value; inp.placeholder=placeholder;
  return inp;
}
function cellSelect(options, placeholder){
  const sel=document.createElement('select');
  options.forEach(o=>{
    const opt=document.createElement('option'); opt.value=o; opt.textContent=o; sel.appendChild(opt);
  });
  return sel;
}

// ---------- 1. LABOR TABLE ----------
const laborBody = document.querySelector('#laborTable tbody');
function addLaborRow(trade='', count=''){
  const tr=document.createElement('tr');
  const td1=document.createElement('td'); td1.appendChild(cellInput('text', trade, 'مثال: سباك'));
  const td2=document.createElement('td'); td2.className='num-cell';
  const countInput = cellInput('number', count, '0');
  countInput.min=0; countInput.addEventListener('input', recalcLaborTotal);
  td2.appendChild(countInput);
  const td3=document.createElement('td'); td3.appendChild(cellInput('text','', 'ملاحظات'));
  const td4=document.createElement('td'); td4.appendChild(makeDelBtn(tr));
  tr.append(td1,td2,td3,td4);
  laborBody.appendChild(tr);
  recalcLaborTotal();
}
function recalcLaborTotal(){
  let total=0;
  laborBody.querySelectorAll('tr td:nth-child(2) input').forEach(i=> total += Number(i.value)||0);
  document.getElementById('laborTotal').textContent = total;
}
['سباك','كهربائي','حداد مسلح','نجار مسلح','مبيّض / محارة','دهان','عامل عادي','مشرف موقع','مشغل معدات']
  .forEach(t=>addLaborRow(t));

// ---------- 2. ATTENDANCE TABLE ----------
const attBody = document.querySelector('#attendanceTable tbody');
function addAttendanceRow(){
  const tr=document.createElement('tr');
  const td1=document.createElement('td'); td1.appendChild(cellInput('text','', 'اسم الموظف'));
  const td2=document.createElement('td'); td2.appendChild(cellInput('text','', 'المسمى الوظيفي'));
  const td3=document.createElement('td'); td3.appendChild(cellInput('time','09:00'));
  const td4=document.createElement('td'); td4.appendChild(cellInput('time','17:00'));
  const td5=document.createElement('td'); td5.appendChild(cellSelect(['حاضر','غائب','استئذان','إجازة','متأخر']));
  const td6=document.createElement('td'); td6.appendChild(cellInput('text','', 'ملاحظات'));
  const td7=document.createElement('td'); td7.appendChild(makeDelBtn(tr));
  tr.append(td1,td2,td3,td4,td5,td6,td7);
  attBody.appendChild(tr);
}
for(let i=0;i<3;i++) addAttendanceRow();

// ---------- 3. WORKS TABLE ----------
const worksBody = document.querySelector('#worksTable tbody');
function addWorkRow(){
  const tr=document.createElement('tr');
  const td1=document.createElement('td'); td1.appendChild(cellInput('text','', 'مثال: أعمال الصب'));
  const td2=document.createElement('td'); td2.appendChild(cellInput('text','', 'وصف العمل المنجز'));
  const td3=document.createElement('td'); const p=cellInput('number','', '0'); p.min=0; p.max=100; td3.appendChild(p);
  const td4=document.createElement('td'); td4.appendChild(cellInput('text','', 'ملاحظات'));
  const td5=document.createElement('td'); td5.appendChild(makeDelBtn(tr));
  tr.append(td1,td2,td3,td4,td5);
  worksBody.appendChild(tr);
}
for(let i=0;i<3;i++) addWorkRow();

// ---------- 4. MATERIALS & EQUIPMENT ----------
const matBody = document.querySelector('#materialsTable tbody');
function addMaterialRow(){
  const tr=document.createElement('tr');
  const td1=document.createElement('td'); td1.appendChild(cellInput('text','', 'مثال: إسمنت'));
  const td2=document.createElement('td'); td2.appendChild(cellInput('number','', '0'));
  const td3=document.createElement('td'); td3.appendChild(cellInput('text','', 'طن / م3 / كيس'));
  const td4=document.createElement('td'); td4.appendChild(cellInput('text','', 'المورد / ملاحظات'));
  const td5=document.createElement('td'); td5.appendChild(makeDelBtn(tr));
  tr.append(td1,td2,td3,td4,td5);
  matBody.appendChild(tr);
}
for(let i=0;i<2;i++) addMaterialRow();

const eqBody = document.querySelector('#equipmentTable tbody');
function addEquipmentRow(){
  const tr=document.createElement('tr');
  const td1=document.createElement('td'); td1.appendChild(cellInput('text','', 'مثال: رافعة برجية'));
  const td2=document.createElement('td'); td2.appendChild(cellSelect(['تعمل','متوقفة','صيانة']));
  const td3=document.createElement('td'); td3.appendChild(cellInput('number','', '0'));
  const td4=document.createElement('td'); td4.appendChild(cellInput('text','', 'ملاحظات'));
  const td5=document.createElement('td'); td5.appendChild(makeDelBtn(tr));
  tr.append(td1,td2,td3,td4,td5);
  eqBody.appendChild(tr);
}
for(let i=0;i<2;i++) addEquipmentRow();

// ---------- IMAGE UPLOAD ----------
function handleUpload(input, gridId, withTag){
  const grid = document.getElementById(gridId);
  Array.from(input.files).forEach(file=>{
    const reader = new FileReader();
    reader.onload = e=>{
      const card = document.createElement('div');
      card.className='photo-card';
      const del = document.createElement('button');
      del.className='del-btn'; del.textContent='✕'; del.onclick=()=>card.remove();
      const img = document.createElement('img'); img.src = e.target.result;
      const body = document.createElement('div'); body.className='photo-body';
      if(withTag){
        const tagSel = cellSelect(['أثناء العمل','قبل الإنجاز','بعد الإنجاز']);
        body.appendChild(tagSel);
      }
      const cap = cellInput('text','', 'وصف الصورة...');
      body.appendChild(cap);
      card.append(del, img, body);
      grid.appendChild(card);
    };
    reader.readAsDataURL(file);
  });
  input.value = '';
}

// ---------- SIGNATURE PADS ----------
document.querySelectorAll('.sigpad').forEach(canvas=>{
  const ctx = canvas.getContext('2d');
  ctx.strokeStyle = '#17242E'; ctx.lineWidth = 2; ctx.lineCap='round';
  let drawing=false, last=null;
  function pos(e){
    const r = canvas.getBoundingClientRect();
    const x = ((e.touches? e.touches[0].clientX : e.clientX) - r.left) * (canvas.width/r.width);
    const y = ((e.touches? e.touches[0].clientY : e.clientY) - r.top) * (canvas.height/r.height);
    return {x,y};
  }
  function start(e){ drawing=true; last=pos(e); e.preventDefault(); }
  function move(e){
    if(!drawing) return;
    const p = pos(e);
    ctx.beginPath(); ctx.moveTo(last.x,last.y); ctx.lineTo(p.x,p.y); ctx.stroke();
    last=p; e.preventDefault();
  }
  function end(){ drawing=false; }
  canvas.addEventListener('mousedown', start);
  canvas.addEventListener('mousemove', move);
  window.addEventListener('mouseup', end);
  canvas.addEventListener('touchstart', start, {passive:false});
  canvas.addEventListener('touchmove', move, {passive:false});
  canvas.addEventListener('touchend', end);
});
function clearSig(btn){
  const canvas = btn.closest('.sig-card').querySelector('canvas');
  canvas.getContext('2d').clearRect(0,0,canvas.width,canvas.height);
}

function finalizeAndPrint(){ window.print(); }
</script>
</body>
</html>
