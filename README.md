<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مركز المساعدة الذكية - نظام قطر للتعليم</title>
    <style>
        :root {
            --qatar-maroon: #8A1538;
            --qatar-gold: #C79900;
            --qatar-dark: #5A0E1F;
            --qatar-light: #F9F5E9;
            --qatar-gray: #F5F5F5;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'Cairo', Tahoma, sans-serif;
            background: linear-gradient(135deg, var(--qatar-light) 0%, #FFFFFF 100%);
            color: #333;
            line-height: 1.6;
        }

        /* Header */
        .header {
            background: linear-gradient(135deg, var(--qatar-maroon) 0%, var(--qatar-dark) 100%);
            color: white;
            padding: 25px 0;
            text-align: center;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }

        .header p {
            font-size: 1.2em;
            opacity: 0.9;
        }

        /* Navigation */
        .nav-container {
            background: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.08);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .nav-btn {
            background: white;
            color: var(--qatar-maroon);
            border: 2px solid var(--qatar-maroon);
            padding: 12px 25px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 1em;
            font-weight: bold;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .nav-btn:hover, .nav-btn.active {
            background: var(--qatar-maroon);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(138, 21, 56, 0.2);
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 30px auto;
            padding: 0 20px;
        }

        .section {
            background: white;
            border-radius: 15px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            display: none;
            border-top: 5px solid var(--qatar-gold);
        }

        .section.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section h2 {
            color: var(--qatar-maroon);
            font-size: 2em;
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 3px solid var(--qatar-gold);
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .icon {
            font-size: 1.3em;
        }

        /* Voice Bot Section */
        .voice-bot-container {
            background: linear-gradient(135deg, var(--qatar-gray) 0%, white 100%);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            border: 2px dashed var(--qatar-gold);
        }

        /* تنسيق خاص لودجت ElevenLabs */
        elevenlabs-convai {
            display: block;
            width: 100% !important;
            height: 500px !important;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            margin: 20px auto;
            border: 2px solid var(--qatar-gold);
        }

        .bot-features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 25px;
        }

        .feature-card {
            background: var(--qatar-gold);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
        }

        .feature-card h4 {
            margin-bottom: 10px;
            font-size: 1.2em;
        }

        /* Password Recovery */
        .recovery-steps {
            background: var(--qatar-gray);
            border-radius: 10px;
            padding: 25px;
            margin: 20px 0;
        }

        .step {
            background: white;
            padding: 20px;
            margin: 15px 0;
            border-radius: 10px;
            border-right: 5px solid var(--qatar-maroon);
            display: flex;
            align-items: center;
            gap: 20px;
            transition: all 0.3s ease;
        }

        .step:hover {
            transform: translateX(-5px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .step-number {
            background: var(--qatar-maroon);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5em;
            font-weight: bold;
            flex-shrink: 0;
        }

        .step-content h4 {
            color: var(--qatar-dark);
            margin-bottom: 8px;
        }

        .video-container {
            background: black;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            text-align: center;
            color: var(--qatar-gold);
            min-height: 400px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2em;
        }

        /* Tools Grid */
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 25px;
        }

        .tool-card {
            background: white;
            border: 2px solid var(--qatar-gray);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tool-card:hover {
            border-color: var(--qatar-maroon);
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(138, 21, 56, 0.1);
        }

        .tool-card h3 {
            color: var(--qatar-maroon);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tool-card .status {
            background: var(--qatar-gold);
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9em;
            display: inline-block;
            margin-top: 10px;
        }

        /* Footer */
        .footer {
            background: var(--qatar-dark);
            color: white;
            text-align: center;
            padding: 30px 0;
            margin-top: 50px;
        }

        .footer p {
            margin: 5px 0;
        }

        .footer a {
            color: var(--qatar-gold);
            text-decoration: none;
        }

        /* Button Styles */
        .btn-primary {
            background: var(--qatar-maroon);
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 30px;
            font-size: 1.1em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            margin: 10px;
        }

        .btn-primary:hover {
            background: var(--qatar-dark);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(138, 21, 56, 0.2);
        }

        .btn-secondary {
            background: var(--qatar-gold);
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 30px;
            font-size: 1.1em;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            margin: 10px;
        }

        .btn-secondary:hover {
            background: #A67C00;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(199, 153, 0, 0.2);
        }

        .alert {
            background: #FFF3CD;
            border: 2px solid var(--qatar-gold);
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
        }

        .alert-icon {
            font-size: 1.5em;
            color: var(--qatar-maroon);
            margin-left: 10px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header h1 { font-size: 2em; }
            .section { padding: 25px; }
            .nav { flex-direction: column; align-items: center; }
            .step { flex-direction: column; text-align: center; }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <h1>🏫 مركز المساعدة الذكية</h1>
        <p>نظام قطر للتعليم - بوابتك الشاملة لجميع الأدوات والدعم الفني</p>
    </header>

    <!-- Navigation -->
    <nav class="nav-container">
        <div class="nav">
            <button class="nav-btn active" onclick="showSection('voice-bot')">
                🤖 المساعد الصوتي
            </button>
            <button class="nav-btn" onclick="showSection('password-recovery')">
                🔐 استعادة كلمة المرور
            </button>
            <button class="nav-btn" onclick="showSection('system-access')">
                💻 الوصول للنظام
            </button>
            <button class="nav-btn" onclick="showSection('tools')">
                🛠️ الأدوات المتكاملة
            </button>
            <button class="nav-btn" onclick="showSection('support')">
                📞 الدعم الفني
            </button>
        </div>
    </nav>

    <!-- Main Container -->
    <div class="container">
        <!-- Voice Bot Section -->
        <section id="voice-bot" class="section active">
            <h2>
                <span class="icon">🤖</span>
                المساعد الصوتي الذكي - EvenLabs
            </h2>
            
            <div class="alert">
                <span class="alert-icon">⚡</span>
                <strong>جديد!</strong> يمكنك الآن التفاعل مع نظام قطر للتعليم عبر الأوامر الصوتية باللغة العربية
            </div>

            <div class="voice-bot-container">
                <h3>🎙️ ابدأ محادثتك الصوتية الآن</h3>
                <p style="margin-bottom: 20px;">اضغط على زر الميكروفون واسألني أي سؤال عن نظام قطر للتعليم</p>
                
                <!-- كود الـ Embed الخاص بـ ElevenLabs -->
                <elevenlabs-convai agent-id="agent_8401k8gg9x9ee0185pwy9tvhkvae"></elevenlabs-convai>
                <script src="https://unpkg.com/@elevenlabs/convai-widget-embed" async type="text/javascript"></script>
                
                <div style="margin-top: 20px;">
                    <button class="btn-primary" onclick="startVoiceSession()">
                        🎤 بدء جلسة صوتية
                    </button>
                    <button class="btn-secondary" onclick="testMicrophone()">
                        🎵 اختبار الميكروفون
                    </button>
                </div>

                <div class="bot-features">
                    <div class="feature-card">
                        <h4>🎤</h4>
                        <p>دعم الأوامر الصوتية باللهجة الخليجية والعربية الفصحى</p>
                    </div>
                    <div class="feature-card">
                        <h4>⚡</h4>
                        <p>استجابة فورية لاستعلاماتك عن التقييمات والدرجات</p>
                    </div>
                    <div class="feature-card">
                        <h4>🔒</h4>
                        <p>خصوصية تامة - جميع البيانات مشفرة</p>
                    </div>
                    <div class="feature-card">
                        <h4>📱</h4>
                        <p>يعمل على جميع الأجهزة (حاسوب، تابلت، هاتف)</p>
                    </div>
                </div>

                <div style="margin-top: 30px; padding: 20px; background: white; border-radius: 10px;">
                    <h4 style="color: var(--qatar-maroon); margin-bottom: 15px;">📋 أمثلة لما يمكنك سؤاله:</h4>
                    <ul style="text-align: right; list-style: none;">
                        <li>✅ "ما هي نسبة إكمال التقييم الأسبوعي لصف 7-1؟"</li>
                        <li>✅ "أريد تقريراً عن طلاب الصف الثامن"</li>
                        <li>✅ "كيف أستعيد كلمة المرور الخاصة بي؟"</li>
                        <li>✅ "ماهي خطوات إنشاء تقييم أسبوعي جديد؟"</li>
                        <li>✅ "أعرض لي إحصائيات المدرسة لهذا الأسبوع"</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Password Recovery Section -->
        <section id="password-recovery" class="section">
            <h2>
                <span class="icon">🔐</span>
                استعادة كلمة المرور - دليلك الشامل
            </h2>

            <div class="alert">
                <span class="alert-icon">⚠️</span>
                <strong>ملاحظة مهمة:</strong> تأكد من إدخال بريدك الإلكتروني المسجل في نظام الوزارة بدقة
            </div>

            <div class="video-container">
                <p>🎥 فيديو تعليمي: شرح مصور لخطوات استعادة كلمة المرور (قريباً)</p>
            </div>

            <h3 style="color: var(--qatar-maroon); margin: 25px 0;">📋 الخطوات التفصيلية:</h3>
            
            <div class="recovery-steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <div class="step-content">
                        <h4>انتقل إلى صفحة تسجيل الدخول</h4>
                        <p>افتح متصفحك واذهب إلى <a href="https://qatar.edu.gov.qa" target="_blank">نظام قطر للتعليم</a></p>
                        <p>اضغط على زر "نسيت كلمة المرور؟" الموجود أسفل خانة تسجيل الدخول</p>
                    </div>
                </div>

                <div class="step">
                    <div class="step-number">2</div>
                    <div class="step-content">
                        <h4>أدخل بريدك الإلكتروني المسجل</h4>
                        <p>اكتب بريدك الإلكتروني بالتنسيق التالي: username@education.qa</p>
                        <p>تأكد من كتابة البريد بدون أخطاء إملائية أو مسافات</p>
                    </div>
                </div>

                <div class="step">
                    <div class="step-number">3</div>
                    <div class="step-content">
                        <h4>تحقق من بريدك الإلكتروني</h4>
                        <p>ستصلك رسالة خلال 2-5 دقائق تحتوي على رابط إعادة تعيين كلمة المرور</p>
                        <p><strong>ملاحظة:</strong> قد تكون الرسالة في مجلد الرسائل غير المرغوب فيها (Spam)</p>
                    </div>
                </div>

                <div class="step">
                    <div class="step-number">4</div>
                    <div class="step-content">
                        <h4>انقر على رابط إعادة التعيين</h4>
                        <p>اضغط على الرابط المرفق في البريد الإلكتروني</p>
                        <p>الرابط صالح لمدة 24 ساعة فقط لأسباب أمنية</p>
                    </div>
                </div>

                <div class="step">
                    <div class="step-number">5</div>
                    <div class="step-content">
                        <h4>أدخل كلمة مرور جديدة</h4>
                        <p>اختر كلمة مرور قوية تتكون من 8 أحرف على الأقل</p>
                        <p>يجب أن تحتوي على: أحرف كبيرة وصغيرة، أرقام، رموز خاصة (@$!%*?&)</p>
                        <p>مثال: Edu@Qatar2025!</p>
                    </div>
                </div>

                <div class="step">
                    <div class="step-number">6</div>
                    <div class="step-content">
                        <h4>تأكيد كلمة المرور وتسجيل الدخول</h4>
                        <p>أعد كتابة كلمة المرور الجديدة للتأكيد</p>
                        <p>اضغط "حفظ" ثم عد إلى صفحة تسجيل الدخول</p>
                    </div>
                </div>
            </div>

            <div style="background: #E8F5E9; border: 2px solid #4CAF50; border-radius: 10px; padding: 20px; margin: 20px 0;">
                <h4 style="color: #2E7D32; margin-bottom: 10px;">✅ تمت العملية بنجاح!</h4>
                <p>يمكنك الآن تسجيل الدخول باستخدام كلمة المرور الجديدة.</p>
            </div>

            <h3 style="color: var(--qatar-maroon); margin: 25px 0 15px;">🚨 المشاكل الشائعة والحلول:</h3>
            
            <div style="background: white; border-radius: 10px; padding: 20px;">
                <div style="margin-bottom: 15px;">
                    <h4 style="color: #D32F2F;">❌ لم تصلني الرسالة؟</h4>
                    <p>• تحقق من مجلد Spam/Junk<br>
                    • تأكد من صحة البريد الإلكتروني<br>
                    • انتظر 5-10 دقائق<br>
                    • حاول مرة أخرى أو تواصل مع الدعم الفني</p>
                </div>
                <div style="margin-bottom: 15px;">
                    <h4 style="color: #D32F2F;">❌ الرابط لا يعمل؟</h4>
                    <p>• الرابط صالح 24 ساعة فقط<br>
                    • تأكد من نسخ الرابط كاملاً<br>
                    • جرب فتحه في متصفح مختلف</p>
                </div>
                <div>
                    <h4 style="color: #D32F2F;">❌ البريد الإلكتروني غير موجود؟</h4>
                    <p>• تأكد من كتابة البريد الصحيح<br>
                    • استخدم البريد الرسمي للوزارة<br>
                    • اتصل بمسؤول النظام في مدرستك</p>
                </div>
            </div>
        </section>

        <!-- System Access Section -->
        <section id="system-access" class="section">
            <h2>
                <span class="icon">💻</span>
                دليل الوصول السريع - نظام قطر للتعليم
            </h2>

            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; margin: 25px 0;">
                <a href="https://qatar.edu.gov.qa" target="_blank" class="tool-card" style="text-align: center; text-decoration: none; color: inherit;">
                    <h3>🏠</h3>
                    <h4>الصفحة الرئيسية</h4>
                    <p>الوصول المباشر لنظام قطر للتعليم</p>
                    <span class="status">🟢 نشط</span>
                </a>
                <a href="https://qatar.edu.gov.qa/teacher/dashboard" target="_blank" class="tool-card" style="text-align: center; text-decoration: none; color: inherit;">
                    <h3>📊</h3>
                    <h4>لوحة المعلم</h4>
                    <p>إدارة الصفوف والتقييمات</p>
                    <span class="status">🟢 نشط</span>
                </a>
                <a href="https://qatar.edu.gov.qa/student/portal" target="_blank" class="tool-card" style="text-align: center; text-decoration: none; color: inherit;">
                    <h3>🎓</h3>
                    <h4>بوابة الطالب</h4>
                    <p>الواجبات والتقييمات الإلكترونية</p>
                    <span class="status">🟢 نشط</span>
                </a>
                <a href="https://qatar.edu.gov.qa/parents" target="_blank" class="tool-card" style="text-align: center; text-decoration: none; color: inherit;">
                    <h3>👨‍👩‍👧‍👦</h3>
                    <h4>بوابة أولياء الأمور</h4>
                    <p>متابعة أداء الطالب</p>
                    <span class="status">🟢 نشط</span>
                </a>
            </div>

            <h3 style="color: var(--qatar-maroon); margin: 30px 0 20px;">📋 متطلبات الدخول:</h3>
            <ul style="background: white; padding: 20px; border-radius: 10px; list-style: none;">
                <li>✅ متصفح حديث (Chrome, Firefox, Edge, Safari)</li>
                <li>✅ اتصال إنترنت مستقر (5 ميجابت/ثانية على الأقل)</li>
                <li>✅ بريد إلكتروني وزاري ساري</li>
                <li>✅ كلمة مرور صالحة</li>
                <li>✅ تمكين JavaScript في المتصفح</li>
            </ul>

            <h3 style="color: var(--qatar-maroon); margin: 30px 0 20px;">🔧 إعدادات المتصفح الموصى بها:</h3>
            <div style="background: var(--qatar-gray); padding: 20px; border-radius: 10px;">
                <div style="margin-bottom: 15px;">
                    <h4>Google Chrome:</h4>
                    <p>الإصدار 110+ | تمكين JavaScript | السماح بالكوكيز</p>
                </div>
                <div style="margin-bottom: 15px;">
                    <h4>Microsoft Edge:</h4>
                    <p>الإصدار 110+ | وضع التوافق مع Chrome</p>
                </div>
                <div>
                    <h4>Firefox:</h4>
                    <p>الإصدار 100+ | تحديث تلقائي مفعل</p>
                </div>
            </div>
        </section>

        <!-- Tools Section -->
        <section id="tools" class="section">
            <h2>
                <span class="icon">🛠️</span>
                الأدوات المتكاملة
            </h2>

            <div class="tools-grid">
                <div class="tool-card">
                    <h3>📊 تطبيق إنجاز</h3>
                    <p>تحليل بيانات التقييمات الأسبوعية بدقة واحترافية</p>
                    <ul style="margin: 10px 0;">
                        <li>✅ تصنيف الطلاب إلى 6 فئات</li>
                        <li>✅ تقارير Excel/PDF</li>
                        <li>✅ مجاني ومفتوح المصدر</li>
                    </ul>
                    <a href="https://ca3xrduq4ttnjbv9arv2va.streamlit.app/" target="_blank" class="btn-primary">
                        فتح التطبيق
                    </a>
                </div>

                <div class="tool-card">
                    <h3>🤖 المساعد الذكي</h3>
                    <p>إجابات فورية على أسئلتك التقنية</p>
                    <ul style="margin: 10px 0;">
                        <li>✅ دعم صوتي ونصي</li>
                        <li>✅ اللغة العربية فقط</li>
                        <li>✅ متاح 24/7</li>
                    </ul>
                    <button class="btn-secondary" onclick="showSection('voice-bot')">
                        استخدام المساعد
                    </button>
                </div>

                <div class="tool-card">
                    <h3>📈 لوحة التحكم المتقدمة</h3>
                    <p>مؤشرات الأداء الرئيسية للمدرسة</p>
                    <ul style="margin: 10px 0;">
                        <li>✅ تحليلات فورية</li>
                        <li>✅ رسوم بيانية تفاعلية</li>
                        <li>✅ مقارنات بين الصفوف</li>
                    </ul>
                    <button class="btn-primary" onclick="alert('قريباً - تحت التطوير')">
                        قريباً
                    </button>
                </div>

                <div class="tool-card">
                    <h3>🔔 نظام التنبيهات</h3>
                    <p>إشعارات فورية للمعلمين والطلاب</p>
                    <ul style="margin: 10px 0;">
                        <li>✅ تنبيهات التقييمات</li>
                        <li>✅ تذكير بالمواعيد</li>
                        <li>✅ متابعة الطلاب المتعثرين</li>
                    </ul>
                    <button class="btn-primary" onclick="alert('قريباً - تحت التطوير')">
                        قريباً
                    </button>
                </div>

                <div class="tool-card">
                    <h3>📱 تطبيق الجوال</h3>
                    <p>متابعة الطلاب من هاتفك</p>
                    <ul style="margin: 10px 0;">
                        <li>✅ Android & iOS</li>
                        <li>✅ واجهة عربية</li>
                        <li>✅ إشعارات فورية</li>
                    </ul>
                    <button class="btn-primary" onclick="alert('قريباً - تحت التطوير')">
                        قريباً
                    </button>
                </div>

                <div class="tool-card">
                    <h3>🤝 المجتمع التعليمي</h3>
                    <p>تواصل وتشارك مع المعلمين</p>
                    <ul style="margin: 10px 0;">
                        <li>✅ منتديات نقاش</li>
                        <li>✅ مشاركة التجارب</li>
                        <li>✅ دعم فني متبادل</li>
                    </ul>
                    <a href="https://www.linkedin.com/in/sahar-osman-a19a45209/" target="_blank" class="btn-secondary">
                        الانضمام
                    </a>
                </div>
            </div>
        </section>

        <!-- Support Section -->
        <section id="support" class="section">
            <h2>
                <span class="icon">📞</span>
                الدعم الفني والمساعدة
            </h2>

            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 25px; margin: 25px 0;">
                <div class="tool-card" style="text-align: center;">
                    <h3>📧 البريد الإلكتروني</h3>
                    <p>سحر عثمان</p>
                    <p><a href="mailto:Othman@edu.gov.qa">Othman@edu.gov.qa</a></p>
                    <p>المدرسة النموذجية</p>
                    <span class="status">🟢 متاح</span>
                </div>

                <div class="tool-card" style="text-align: center;">
                    <h3>👩‍💼 منسقة التعلم الإلكتروني</h3>
                    <p>سحر عثمان</p>
                    <p><a href="mailto:S.mahgoub0101@education.qa">S.mahgoub0101@education.qa</a></p>
                    <p>وزارة التعليم</p>
                    <span class="status">🟢 متاح</span>
                </div>

                <div class="tool-card" style="text-align: center;">
                    <h3>🔗 LinkedIn</h3>
                    <p>للتواصل المهني</p>
                    <p><a href="https://www.linkedin.com/in/sahar-osman-a19a45209/" target="_blank">Sahar Osman</a></p>
                    <p>مستشار تعليمي</p>
                    <span class="status">🟢 متاح</span>
                </div>
            </div>

            <div style="background: var(--qatar-gray); border-radius: 10px; padding: 25px; margin: 25px 0;">
                <h3 style="color: var(--qatar-maroon); margin-bottom: 15px;">🕒 أوقات العمل:</h3>
                <ul style="list-style: none;">
                    <li>📅 الأحد - الخميس: 7:00 صباحاً - 2:00 مساءً</li>
                    <li>📅 الجمعة - السبت: إجازة رسمية</li>
                    <li>⏱️ وقت الاستجابة: خلال 24 ساعة عمل</li>
                </ul>
            </div>

            <div class="alert">
                <span class="alert-icon">💡</span>
                <strong>نصيحة:</strong> قبل التواصل مع الدعم الفني، تأكد من:
                <ul style="margin-top: 10px;">
                    <li>✅ استخدام بريدك الإلكتروني الوزاري</li>
                    <li>✅ توضيح المشكلة بشكل دقيق</li>
                    <li>✅ إرفاق لقطة شاشة إن أمكن</li>
                    <li>✅ ذكر رقم تعريفك الوظيفي</li>
                </ul>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <p>© 2025 - جميع الحقوق محفوظة - وزارة التعليم والتعليم العالي - دولة قطر</p>
        <p>تصميم وتطوير: <a href="https://www.linkedin.com/in/sahar-osman-a19a45209/" target="_blank">سحر عثمان</a></p>
        <p>باستخدام الذكاء الاصطناعي التوليدي 🤖</p>
        <p style="margin-top: 15px; font-style: italic;">"متعلم ريادي لتنمية مستدامة" - رؤية قطر 2030</p>
    </footer>

    <script>
        // Navigation functionality
        function showSection(sectionId) {
            // Hide all sections
            const sections = document.querySelectorAll('.section');
            sections.forEach(section => {
                section.classList.remove('active');
            });
            
            // Remove active class from all nav buttons
            const navBtns = document.querySelectorAll('.nav-btn');
            navBtns.forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Show selected section
            document.getElementById(sectionId).classList.add('active');
            
            // Add active class to clicked button
            event.target.classList.add('active');
        }

        // Voice bot functions
        function startVoiceSession() {
            alert('جاري بدء جلسة صوتية... \n\nيرجى السماح بالوصول للميكروفون عند الطلب.\n\nملاحظة: هذا مثال توضيحي. في الواقع، سيتم تفعيل البوت الصوتي من EvenLabs.');
            // In real implementation, this would initialize the EvenLabs bot
        }

        function testMicrophone() {
            alert('جاري اختبار الميكروفون...\n\nتأكد من ظهور المؤشر الصوتي.\n\nملاحظة: هذا مثال توضيحي.');
        }

        // Add smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Auto-resize iframe
        window.addEventListener('load', function() {
            const iframe = document.querySelector('.bot-iframe');
            if (iframe) {
                iframe.onload = function() {
                    // Auto-resize logic would go here
                    console.log('Bot iframe loaded successfully');
                };
            }
        });
    </script>
</body>
</html>
