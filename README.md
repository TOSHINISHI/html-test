<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GameStream AI - 24時間365日AIゲーム配信プラットフォーム</title>
    <style>
        :root {
            --primary: #6C5CE7;
            --secondary: #00CEFF;
            --dark: #2D3436;
            --light: #FFFFFF;
            --accent: #FD79A8;
            --gradient: linear-gradient(90deg, var(--primary), var(--secondary));
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Helvetica Neue', sans-serif;
        }

        body {
            background-color: #0F1923;
            color: var(--light);
            line-height: 1.6;
        }

        header {
            background: var(--dark);
            padding: 1.5rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--secondary);
        }

        .btn {
            display: inline-block;
            background: var(--gradient);
            color: var(--light);
            padding: 0.8rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s, box-shadow 0.3s;
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(108, 92, 231, 0.4);
        }

        .hero {
            padding: 180px 0 100px;
            text-align: center;
            background: radial-gradient(circle at center, #1A2634, #0F1923);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            background: url('/api/placeholder/1200/600') center/cover no-repeat;
            opacity: 0.1;
            z-index: 0;
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
        }

        h1 span {
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .subtitle {
            font-size: 1.5rem;
            margin-bottom: 2.5rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            color: #DFE6E9;
        }

        .feature-section {
            padding: 100px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 4rem;
        }

        .section-title span {
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background: rgba(45, 52, 54, 0.6);
            border-radius: 10px;
            padding: 2rem;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
        }

        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .how-it-works {
            padding: 100px 0;
            background: #131F2F;
        }

        .steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            margin-top: 4rem;
        }

        .step {
            text-align: center;
            position: relative;
        }

        .step-number {
            background: var(--gradient);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: 700;
            font-size: 1.5rem;
            margin: 0 auto 1.5rem;
        }

        .step-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .pricing {
            padding: 100px 0;
        }

        .pricing-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .pricing-card {
            background: rgba(45, 52, 54, 0.6);
            border-radius: 10px;
            padding: 3rem 2rem;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .pricing-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .popular {
            border: 2px solid var(--primary);
            position: relative;
        }

        .popular::before {
            content: "人気";
            position: absolute;
            top: -15px;
            right: 30px;
            background: var(--primary);
            color: var(--light);
            padding: 0.5rem 1rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .pricing-title {
            font-size: 1.8rem;
            margin-bottom: 1rem;
        }

        .pricing-price {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 2rem;
        }

        .pricing-price span {
            font-size: 1rem;
            font-weight: 400;
        }

        .pricing-features {
            list-style: none;
            margin-bottom: 2rem;
        }

        .pricing-features li {
            padding: 0.5rem 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .testimonials {
            padding: 100px 0;
            background: #131F2F;
        }

        .testimonial-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .testimonial-card {
            background: rgba(45, 52, 54, 0.6);
            border-radius: 10px;
            padding: 2rem;
            position: relative;
        }

        .testimonial-text {
            margin-bottom: 1.5rem;
            font-style: italic;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
        }

        .testimonial-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            margin-right: 1rem;
            background: var(--dark);
        }

        .testimonial-name {
            font-weight: 600;
        }

        .testimonial-position {
            font-size: 0.9rem;
            color: #B2BEC3;
        }

        .cta {
            padding: 100px 0;
            text-align: center;
        }

        .cta-title {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }

        .cta-text {
            font-size: 1.2rem;
            margin-bottom: 2.5rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        footer {
            background: var(--dark);
            padding: 4rem 0 2rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }

        .footer-column h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.8rem;
        }

        .footer-links a {
            color: #B2BEC3;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: var(--secondary);
        }

        .footer-bottom {
            margin-top: 3rem;
            text-align: center;
            color: #B2BEC3;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 700;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1.2rem;
        }

        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                gap: 1rem;
            }

            .nav-links {
                flex-direction: column;
                gap: 1rem;
                text-align: center;
            }

            h1 {
                font-size: 2.5rem;
            }

            .subtitle {
                font-size: 1.2rem;
            }

            .section-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo">GameStream AI</div>
                <div class="nav-links">
                    <a href="#features">機能</a>
                    <a href="#how-it-works">使い方</a>
                    <a href="#pricing">料金</a>
                    <a href="#testimonials">お客様の声</a>
                </div>
                <a href="#cta" class="btn">無料で始める</a>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container hero-content">
            <h1>AIで<span>24時間365日</span>あなたのゲームを配信</h1>
            <p class="subtitle">人間のストリーマーのように自然な会話とプレイスタイルで、寝ている間も稼ぎ続けるAIゲーム配信プラットフォーム</p>
            <a href="#cta" class="btn">14日間無料トライアル</a>
        </div>
    </section>

    <section class="feature-section" id="features">
        <div class="container">
            <h2 class="section-title">なぜ <span>GameStream AI</span> なのか</h2>
            <div class="features">
                <div class="feature-card">
                    <div class="feature-icon">🎮</div>
                    <h3 class="feature-title">24時間365日配信</h3>
                    <p>あなたが寝ている間も、仕事中も、AIがあなたの代わりにゲームを配信し続けます。視聴者とのエンゲージメントを最大化しましょう。</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🤖</div>
                    <h3 class="feature-title">自然な会話AIモデル</h3>
                    <p>最先端の自然言語処理技術により、AIが視聴者とリアルタイムで自然な会話を行います。人間のストリーマーと見分けがつきません。</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <h3 class="feature-title">詳細な分析ダッシュボード</h3>
                    <p>視聴者数、エンゲージメント率、収益などのデータをリアルタイムで確認。AIのパフォーマンスを常に最適化できます。</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🎯</div>
                    <h3 class="feature-title">ゲームプレイAI</h3>
                    <p>初心者から上級者まで、様々なスキルレベルでゲームをプレイするAIを設定可能。あなたのプレイスタイルを学習し再現します。</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">💰</div>
                    <h3 class="feature-title">収益化サポート</h3>
                    <p>スーパーチャット、サブスクリプション、広告収入などの収益化機能を完全サポート。寝ている間も収益を生み出します。</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔒</div>
                    <h3 class="feature-title">セキュリティ対策</h3>
                    <p>不適切なコメントや荒らし行為をAIが自動で検知・対応。常に安全な配信環境を維持します。</p>
                </div>
            </div>
            
            <div class="stats-container">
                <div class="stat-item">
                    <div class="stat-number">10,000+</div>
                    <div class="stat-label">アクティブユーザー</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">500万+</div>
                    <div class="stat-label">月間視聴時間</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">98%</div>
                    <div class="stat-label">顧客満足度</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">300%</div>
                    <div class="stat-label">平均収益増加率</div>
                </div>
            </div>
        </div>
    </section>

    <section class="how-it-works" id="how-it-works">
        <div class="container">
            <h2 class="section-title">GameStream AI <span>の使い方</span></h2>
            <div class="steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3 class="step-title">アカウント作成</h3>
                    <p>数分で簡単に登録できます。Twitch、YouTube、Bilibili、ニコニコ生放送などの主要プラットフォームと連携可能。</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3 class="step-title">AIの学習</h3>
                    <p>あなたの過去の配信データをAIに学習させることで、あなたの話し方やプレイスタイルを再現します。また、最初から設定することも可能です。</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3 class="step-title">ゲーム設定</h3>
                    <p>配信するゲームとAIの難易度を選択。対応ゲームは200タイトル以上、常に増え続けています。</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3 class="step-title">配信スケジュール</h3>
                    <p>AIが配信する時間帯を設定。完全自動化も、あなたの配信と組み合わせることも可能です。</p>
                </div>
                <div class="step">
                    <div class="step-number">5</div>
                    <h3 class="step-title">収益管理</h3>
                    <p>配信からの収益を確認・管理。毎月の収益レポートも自動で生成されます。</p>
                </div>
            </div>
        </div>
    </section>

    <section class="pricing" id="pricing">
        <div class="container">
            <h2 class="section-title">シンプルな <span>料金プラン</span></h2>
            <div class="pricing-cards">
                <div class="pricing-card">
                    <h3 class="pricing-title">スタータープラン</h3>
                    <div class="pricing-price">¥4,980<span>/月</span></div>
                    <ul class="pricing-features">
                        <li>1日8時間の配信時間</li>
                        <li>基本的なAI会話モデル</li>
                        <li>5ゲームまで対応</li>
                        <li>基本的な分析ダッシュボード</li>
                        <li>Email サポート</li>
                    </ul>
                    <a href="#cta" class="btn">選択する</a>
                </div>
                <div class="pricing-card popular">
                    <h3 class="pricing-title">プロフェッショナル</h3>
                    <div class="pricing-price">¥9,980<span>/月</span></div>
                    <ul class="pricing-features">
                        <li>24時間365日無制限配信</li>
                        <li>高度なAI会話モデル</li>
                        <li>20ゲームまで対応</li>
                        <li>詳細な分析ダッシュボード</li>
                        <li>優先サポート</li>
                        <li>収益化コンサルティング</li>
                    </ul>
                    <a href="#cta" class="btn">選択する</a>
                </div>
                <div class="pricing-card">
                    <h3 class="pricing-title">エンタープライズ</h3>
                    <div class="pricing-price">¥29,980<span>/月</span></div>
                    <ul class="pricing-features">
                        <li>複数チャンネル対応</li>
                        <li>カスタムAIモデル</li>
                        <li>無制限ゲーム対応</li>
                        <li>AIキャラクターカスタマイズ</li>
                        <li>専属サポートマネージャー</li>
                        <li>ホワイトラベル対応</li>
                    </ul>
                    <a href="#cta" class="btn">お問い合わせ</a>
                </div>
            </div>
        </div>
    </section>

    <section class="testimonials" id="testimonials">
        <div class="container">
            <h2 class="section-title">お客様の <span>声</span></h2>
            <div class="testimonial-cards">
                <div class="testimonial-card">
                    <p class="testimonial-text">「GameStream AIのおかげで、寝ている間も配信が続き、海外の視聴者も増えました。月の収益が3倍になり、驚いています。」</p>
                    <div class="testimonial-author">
                        <div class="testimonial-avatar"></div>
                        <div>
                            <div class="testimonial-name">ゲーム太郎</div>
                            <div class="testimonial-position">プロゲーマー / 10万フォロワー</div>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <p class="testimonial-text">「仕事と配信の両立が難しかったのですが、AIが私の代わりに配信してくれるおかげで、チャンネルの成長が止まりませんでした。視聴者からもAIだと気づかれないほど自然です。」</p>
                    <div class="testimonial-author">
                        <div class="testimonial-avatar"></div>
                        <div>
                            <div class="testimonial-name">配信子</div>
                            <div class="testimonial-position">VTuber / 5万フォロワー</div>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <p class="testimonial-text">「最初は半信半疑でしたが、GameStream AIの設定は簡単で、すぐに使い始められました。AIが私のプレイスタイルをよく再現していて、ファンからの評判も上々です。」</p>
                    <div class="testimonial-author">
                        <div class="testimonial-avatar"></div>
                        <div>
                            <div class="testimonial-name">ストリームマスター</div>
                            <div class="testimonial-position">インディーゲーム開発者 / 3万フォロワー</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="cta" id="cta">
        <div class="container">
            <h2 class="cta-title">今すぐ始めましょう</h2>
            <p class="cta-text">14日間の無料トライアルで、GameStream AIの可能性を体験してください。契約不要、いつでもキャンセル可能です。</p>
            <a href="#" class="btn">無料で始める</a>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>GameStream AI</h3>
                    <p>24時間365日、AIであなたのゲームを配信するプラットフォーム。</p>
                </div>
                <div class="footer-column">
                    <h3>リンク</h3>
                    <ul class="footer-links">
                        <li><a href="#features">機能</a></li>
                        <li><a href="#how-it-works">使い方</a></li>
                        <li><a href="#pricing">料金</a></li>
                        <li><a href="#testimonials">お客様の声</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>サポート</h3>
                    <ul class="footer-links">
                        <li><a href="#">よくある質問</a></li>
                        <li><a href="#">お問い合わせ</a></li>
                        <li><a href="#">ドキュメント</a></li>
                        <li><a href="#">ステータス</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>会社情報</h3>
                    <ul class="footer-links">
                        <li><a href="#">会社概要</a></li>
                        <li><a href="#">プライバシーポリシー</a></li>
                        <li><a href="#">利用規約</a></li>
                        <li><a href="#">採用情報</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 GameStream AI. All rights reserved.</p>
            </div>
        </div>
    </footer>
</body>
</html>
