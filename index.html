<?php
/**
 * Feri Bayarin — Website PPOB (Payment Point Online Bank)
 * Satu file: index.php · Data dummy · Responsive (mobile, tablet, desktop)
 *
 * Jalankan:  php -S localhost:8000   lalu buka http://localhost:8000
 * Login demo: admin@admin.com / 123456
 * Endpoint JSON dummy (perlu login):  index.php?api=products | ?api=transactions | ?api=user
 */

date_default_timezone_set('Asia/Jakarta');

/* =========================================================
 *  AUTENTIKASI (session PHP, akun dummy)
 * ========================================================= */
const ADMIN_EMAIL = 'admin@admin.com';
const ADMIN_PASS  = '123456';

// Saat dijalankan lewat CLI (php index.php > preview.html) halaman login & dashboard
// dirender bersamaan dan login dicek di browser, supaya bisa dipratinjau tanpa server.
$preview = PHP_SAPI === 'cli';

if (!$preview) {
    session_set_cookie_params(['httponly' => true, 'samesite' => 'Lax']);
    session_start();
    if (empty($_SESSION['csrf'])) $_SESSION['csrf'] = bin2hex(random_bytes(16));
}
$authed = !$preview && !empty($_SESSION['auth']);
$loginError = '';
$oldEmail = '';

if (!$preview && isset($_GET['logout'])) {
    $_SESSION = [];
    session_destroy();
    header('Location: ' . strtok($_SERVER['REQUEST_URI'], '?'));
    exit;
}

if (!$preview && ($_POST['action'] ?? '') === 'login') {
    $email = strtolower(trim($_POST['email'] ?? ''));
    $pass  = (string) ($_POST['password'] ?? '');
    $oldEmail = $email;
    $isAjax = ($_SERVER['HTTP_X_REQUESTED_WITH'] ?? '') === 'fetch';
    if (!hash_equals($_SESSION['csrf'], $_POST['csrf'] ?? '')) {
        $loginError = 'Sesi kedaluwarsa. Muat ulang halaman lalu coba lagi.';
    } elseif ($email === '' || $pass === '') {
        $loginError = 'Email dan password wajib diisi.';
    } elseif (hash_equals(ADMIN_EMAIL, $email) && hash_equals(ADMIN_PASS, $pass)) {
        session_regenerate_id(true);
        $_SESSION['auth'] = ['email' => $email, 'at' => time()];
        if ($isAjax) { header('Content-Type: application/json'); echo json_encode(['ok' => true]); exit; }
        header('Location: ' . strtok($_SERVER['REQUEST_URI'], '?'));
        exit;
    } else {
        $loginError = 'Email atau password salah.';
    }
    if ($isAjax) { header('Content-Type: application/json'); echo json_encode(['ok' => false, 'error' => $loginError]); exit; }
}

$showApp   = $authed || $preview;
$showLogin = !$authed || $preview;

/* =========================================================
 *  DATA DUMMY
 * ========================================================= */
$user = [
    'name'    => 'Admin Feri',
    'id'      => 'BYR-208471',
    'phone'   => '0812-3456-7890',
    'email'   => 'admin@admin.com',
    'level'   => 'Agen Gold',
    'saldo'   => 1250000,
    'poin'    => 3420,
    'joined'  => '12 Maret 2024',
];

$categories = [
    ['key' => 'pulsa',   'name' => 'Pulsa',          'type' => 'prepaid',  'input' => 'Nomor HP',         'ph' => '0812xxxxxxxx'],
    ['key' => 'data',    'name' => 'Paket Data',     'type' => 'prepaid',  'input' => 'Nomor HP',         'ph' => '0812xxxxxxxx'],
    ['key' => 'pln',     'name' => 'Token PLN',      'type' => 'prepaid',  'input' => 'ID Pelanggan / No. Meter', 'ph' => '5321xxxxxxx'],
    ['key' => 'plnpasca','name' => 'PLN Pascabayar', 'type' => 'postpaid', 'input' => 'ID Pelanggan',     'ph' => '5321xxxxxxx'],
    ['key' => 'pdam',    'name' => 'PDAM',           'type' => 'postpaid', 'input' => 'No. Pelanggan',    'ph' => '0102xxxxxx'],
    ['key' => 'bpjs',    'name' => 'BPJS Kesehatan', 'type' => 'postpaid', 'input' => 'No. VA Keluarga',  'ph' => '88888xxxxxxxxxxx'],
    ['key' => 'ewallet', 'name' => 'E-Wallet',       'type' => 'prepaid',  'input' => 'Nomor HP Terdaftar','ph' => '0812xxxxxxxx'],
    ['key' => 'game',    'name' => 'Voucher Game',   'type' => 'prepaid',  'input' => 'User ID (Server)', 'ph' => '12345678 (1234)'],
    ['key' => 'tv',      'name' => 'TV Kabel',       'type' => 'postpaid', 'input' => 'No. Pelanggan',    'ph' => '7012xxxxxx'],
    ['key' => 'internet','name' => 'Internet Rumah', 'type' => 'postpaid', 'input' => 'No. Pelanggan',    'ph' => '1223xxxxxxx'],
];

$products = [
    'pulsa' => [
        ['code' => 'P5',   'name' => 'Pulsa 5.000',    'price' => 6200,   'desc' => 'Masa aktif +7 hari'],
        ['code' => 'P10',  'name' => 'Pulsa 10.000',   'price' => 10950,  'desc' => 'Masa aktif +15 hari'],
        ['code' => 'P20',  'name' => 'Pulsa 20.000',   'price' => 20850,  'desc' => 'Masa aktif +30 hari'],
        ['code' => 'P25',  'name' => 'Pulsa 25.000',   'price' => 25700,  'desc' => 'Masa aktif +30 hari'],
        ['code' => 'P50',  'name' => 'Pulsa 50.000',   'price' => 50100,  'desc' => 'Masa aktif +45 hari'],
        ['code' => 'P100', 'name' => 'Pulsa 100.000',  'price' => 99250,  'desc' => 'Masa aktif +60 hari'],
        ['code' => 'P200', 'name' => 'Pulsa 200.000',  'price' => 197800, 'desc' => 'Masa aktif +90 hari'],
        ['code' => 'P500', 'name' => 'Pulsa 500.000',  'price' => 493500, 'desc' => 'Masa aktif +120 hari'],
    ],
    'data' => [
        ['code' => 'D1',  'name' => '2 GB · 7 Hari',     'price' => 12500,  'desc' => 'Kuota utama 24 jam'],
        ['code' => 'D2',  'name' => '6 GB · 30 Hari',    'price' => 29900,  'desc' => '3 GB utama + 3 GB lokal'],
        ['code' => 'D3',  'name' => '12 GB · 30 Hari',   'price' => 52000,  'desc' => 'Termasuk 2 GB apps'],
        ['code' => 'D4',  'name' => '25 GB · 30 Hari',   'price' => 84500,  'desc' => 'Kuota utama 24 jam'],
        ['code' => 'D5',  'name' => '50 GB · 30 Hari',   'price' => 128000, 'desc' => 'Bonus 5 GB malam'],
        ['code' => 'D6',  'name' => 'Unlimited Harian',  'price' => 4500,   'desc' => 'FUP 1 GB / 1 hari'],
    ],
    'pln' => [
        ['code' => 'T20',  'name' => 'Token 20.000',   'price' => 21500,   'desc' => '± 13,1 kWh (R1/1300VA)'],
        ['code' => 'T50',  'name' => 'Token 50.000',   'price' => 51500,   'desc' => '± 32,8 kWh (R1/1300VA)'],
        ['code' => 'T100', 'name' => 'Token 100.000',  'price' => 101500,  'desc' => '± 65,6 kWh (R1/1300VA)'],
        ['code' => 'T200', 'name' => 'Token 200.000',  'price' => 201500,  'desc' => '± 131,2 kWh (R1/1300VA)'],
        ['code' => 'T500', 'name' => 'Token 500.000',  'price' => 501500,  'desc' => '± 328,0 kWh (R1/1300VA)'],
        ['code' => 'T1J',  'name' => 'Token 1.000.000','price' => 1001500, 'desc' => '± 656,1 kWh (R1/1300VA)'],
    ],
    'ewallet' => [
        ['code' => 'GP50',  'name' => 'GoPay 50.000',     'price' => 51000,  'desc' => 'Admin Rp1.000'],
        ['code' => 'GP100', 'name' => 'GoPay 100.000',    'price' => 101000, 'desc' => 'Admin Rp1.000'],
        ['code' => 'OV50',  'name' => 'OVO 50.000',       'price' => 51500,  'desc' => 'Admin Rp1.500'],
        ['code' => 'OV100', 'name' => 'OVO 100.000',      'price' => 101500, 'desc' => 'Admin Rp1.500'],
        ['code' => 'DN50',  'name' => 'DANA 50.000',      'price' => 51000,  'desc' => 'Admin Rp1.000'],
        ['code' => 'SP100', 'name' => 'ShopeePay 100.000','price' => 101000, 'desc' => 'Admin Rp1.000'],
    ],
    'game' => [
        ['code' => 'ML86',  'name' => '86 Diamonds',       'price' => 23500,  'desc' => 'Mobile Legends'],
        ['code' => 'ML172', 'name' => '172 Diamonds',      'price' => 46000,  'desc' => 'Mobile Legends'],
        ['code' => 'FF140', 'name' => '140 Diamonds',      'price' => 19500,  'desc' => 'Free Fire'],
        ['code' => 'FF355', 'name' => '355 Diamonds',      'price' => 48500,  'desc' => 'Free Fire'],
        ['code' => 'PB60',  'name' => '60 UC',             'price' => 14800,  'desc' => 'PUBG Mobile'],
        ['code' => 'GI60',  'name' => '60 Genesis Crystal','price' => 15900,  'desc' => 'Genshin Impact'],
    ],
];

$transactions = [
    ['id' => 'TRX2610190012', 'date' => '2026-10-19 14:22', 'cat' => 'pln',      'product' => 'Token PLN 100.000',    'target' => '532110987654', 'amount' => 101500, 'status' => 'Sukses',  'sn' => '4821-0937-1166-2254-8790'],
    ['id' => 'TRX2610190008', 'date' => '2026-10-19 09:05', 'cat' => 'pulsa',    'product' => 'Telkomsel 50.000',     'target' => '081234567890', 'amount' => 50100,  'status' => 'Sukses',  'sn' => '0419210590331'],
    ['id' => 'TRX2610180041', 'date' => '2026-10-18 20:47', 'cat' => 'game',     'product' => '172 Diamonds ML',      'target' => '84512033 (2190)', 'amount' => 46000, 'status' => 'Pending', 'sn' => '-'],
    ['id' => 'TRX2610180027', 'date' => '2026-10-18 16:13', 'cat' => 'pdam',     'product' => 'PDAM Tirta Kerta Raharja','target' => '0102445881', 'amount' => 127800, 'status' => 'Sukses',  'sn' => 'REF8812004417'],
    ['id' => 'TRX2610170033', 'date' => '2026-10-17 11:30', 'cat' => 'data',     'product' => 'XL 25 GB · 30 Hari',   'target' => '081788812345', 'amount' => 84500,  'status' => 'Gagal',   'sn' => '-'],
    ['id' => 'TRX2610160019', 'date' => '2026-10-16 08:44', 'cat' => 'bpjs',     'product' => 'BPJS Kesehatan 3 Jiwa','target' => '8888801234567890', 'amount' => 316500, 'status' => 'Sukses', 'sn' => 'BPJS-77120884'],
    ['id' => 'TRX2610150006', 'date' => '2026-10-15 19:58', 'cat' => 'ewallet',  'product' => 'DANA 50.000',          'target' => '085712345678', 'amount' => 51000,  'status' => 'Sukses',  'sn' => 'DN0915578812'],
    ['id' => 'TRX2610140021', 'date' => '2026-10-14 13:16', 'cat' => 'plnpasca', 'product' => 'PLN Pascabayar Okt',   'target' => '532200118473', 'amount' => 412350, 'status' => 'Sukses',  'sn' => 'PLNP-0091284471'],
    ['id' => 'TRX2610120015', 'date' => '2026-10-12 07:22', 'cat' => 'internet', 'product' => 'IndiHome Okt 2026',    'target' => '122340098871', 'amount' => 346500, 'status' => 'Sukses',  'sn' => 'IH-55102938'],
];

$deposits = [
    ['method' => 'BCA Virtual Account',     'code' => 'bca',     'fee' => 0],
    ['method' => 'Mandiri Virtual Account', 'code' => 'mandiri', 'fee' => 0],
    ['method' => 'BRI Virtual Account',     'code' => 'bri',     'fee' => 0],
    ['method' => 'QRIS',                    'code' => 'qris',    'fee' => 0.007],
    ['method' => 'Alfamart / Indomaret',    'code' => 'retail',  'fee' => 2500],
];

$promos = [
    ['title' => 'Cashback 10% Token PLN', 'sub' => 'Maks. Rp5.000 · s.d. 31 Okt 2026', 'code' => 'PLNHEMAT'],
    ['title' => 'Diskon Rp2.000 Paket Data', 'sub' => 'Min. transaksi Rp50.000', 'code' => 'DATAKITA'],
    ['title' => 'Poin 2x Bayar BPJS',       'sub' => 'Setiap Senin & Kamis', 'code' => 'SEHAT2X'],
];

$spending = [ // pengeluaran 6 bulan terakhir (Rp)
    ['m' => 'Mei', 'v' => 812000], ['m' => 'Jun', 'v' => 1045000], ['m' => 'Jul', 'v' => 934500],
    ['m' => 'Agu', 'v' => 1268000], ['m' => 'Sep', 'v' => 1102300], ['m' => 'Okt', 'v' => 1536250],
];

/* =========================================================
 *  API JSON SEDERHANA (dummy)
 * ========================================================= */
if (isset($_GET['api'])) {
    header('Content-Type: application/json; charset=utf-8');
    if (!$authed && !$preview) {
        http_response_code(401);
        echo json_encode(['ok' => false, 'error' => 'Silakan login terlebih dahulu']);
        exit;
    }
    $map = [
        'user'         => $user,
        'products'     => ['categories' => $categories, 'items' => $products],
        'transactions' => $transactions,
        'deposits'     => $deposits,
    ];
    $key = $_GET['api'];
    echo json_encode(isset($map[$key]) ? ['ok' => true, 'data' => $map[$key]] : ['ok' => false, 'error' => 'Endpoint tidak ditemukan'], JSON_PRETTY_PRINT);
    exit;
}

function rupiah($n) { return 'Rp' . number_format($n, 0, ',', '.'); }
$hour = (int) date('G');
$greet = $hour < 11 ? 'Selamat pagi' : ($hour < 15 ? 'Selamat siang' : ($hour < 18 ? 'Selamat sore' : 'Selamat malam'));
$firstName = explode(' ', $user['name'])[0];
$h = fn($s) => htmlspecialchars((string) $s, ENT_QUOTES, 'UTF-8');

$appData = json_encode([
    'user' => $user, 'categories' => $categories, 'products' => $products,
    'transactions' => $transactions, 'deposits' => $deposits, 'promos' => $promos, 'spending' => $spending,
], JSON_UNESCAPED_UNICODE | JSON_HEX_TAG);
?>
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Feri Bayarin PPOB</title>
<meta name="claude:viewport-fit-sides" content="cover">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=JetBrains+Mono:wght@500;600&display=swap">
<style>
/* Layout: sidebar kiri (desktop) / bottom-nav (mobile); konten satu kolom berlapis kartu fungsional */
:root{
  --bg:#eef3f1; --surface:#ffffff; --surface-2:#f6f9f8; --line:#dbe5e1;
  --ink:#10292b; --muted:#5d7472;
  --brand:#0b6e60; --brand-ink:#ffffff; --brand-soft:#d8efe9;
  --accent:#e8952b; --accent-soft:#fdf0dc;
  --ok:#1a8a4a; --ok-soft:#ddf3e5; --warn:#b26b00; --warn-soft:#fdf0d6; --bad:#c23b32; --bad-soft:#fbe3e1;
  --hero1:#0b6e60; --hero2:#0a4f48;
  --shadow:0 1px 2px rgba(16,41,43,.06),0 8px 24px -12px rgba(16,41,43,.18);
  --f-body:"Plus Jakarta Sans",system-ui,-apple-system,"Segoe UI",Roboto,sans-serif;
  --f-mono:"JetBrains Mono",ui-monospace,SFMono-Regular,Menlo,monospace;
  --r:14px; --nav-h:64px; --side-w:248px;
}
@media (prefers-color-scheme: dark){:root:not([data-theme="light"]){
  --bg:#0c1615; --surface:#13201f; --surface-2:#182826; --line:#243634;
  --ink:#e4efec; --muted:#93aaa6;
  --brand:#33b39c; --brand-ink:#04211c; --brand-soft:#173a34;
  --accent:#f0a948; --accent-soft:#3a2b14;
  --ok:#4ccb7f; --ok-soft:#163423; --warn:#f0b04a; --warn-soft:#3a2c12; --bad:#f07068; --bad-soft:#3b1a18;
  --hero1:#0f5248; --hero2:#0a312c;
  --shadow:0 1px 2px rgba(0,0,0,.3),0 8px 24px -12px rgba(0,0,0,.6);
  color-scheme:dark;}}
:root[data-theme="dark"]{
  --bg:#0c1615; --surface:#13201f; --surface-2:#182826; --line:#243634;
  --ink:#e4efec; --muted:#93aaa6;
  --brand:#33b39c; --brand-ink:#04211c; --brand-soft:#173a34;
  --accent:#f0a948; --accent-soft:#3a2b14;
  --ok:#4ccb7f; --ok-soft:#163423; --warn:#f0b04a; --warn-soft:#3a2c12; --bad:#f07068; --bad-soft:#3b1a18;
  --hero1:#0f5248; --hero2:#0a312c;
  --shadow:0 1px 2px rgba(0,0,0,.3),0 8px 24px -12px rgba(0,0,0,.6);
  color-scheme:dark;}

*{box-sizing:border-box}
html,body{margin:0}
body{background:var(--bg);color:var(--ink);font-family:var(--f-body);font-size:15px;line-height:1.5;-webkit-font-smoothing:antialiased}
[hidden]{display:none!important}
button,input,select{font:inherit;color:inherit}
button{cursor:pointer}
:focus-visible{outline:2px solid var(--brand);outline-offset:2px;border-radius:6px}
.num{font-family:var(--f-mono);font-variant-numeric:tabular-nums;letter-spacing:-.01em}
h1,h2,h3{margin:0;text-wrap:balance;line-height:1.2}
.ico{width:22px;height:22px;flex:none;stroke:currentColor;fill:none;stroke-width:1.8;stroke-linecap:round;stroke-linejoin:round}

/* ---------- Shell ---------- */
.app{display:flex;min-height:100vh}
.side{display:none}
.main{flex:1;min-width:0;padding-bottom:calc(var(--nav-h) + 24px + env(safe-area-inset-bottom,0px))}
.topbar{position:sticky;top:env(safe-area-inset-top,0px);z-index:20;background:color-mix(in srgb,var(--bg) 88%,transparent);backdrop-filter:blur(10px);border-bottom:1px solid var(--line)}
body::before{content:"";position:fixed;inset:0 0 auto;height:env(safe-area-inset-top,0px);z-index:10;background:var(--bg)}
.topbar-in,.wrap{max-width:1080px;margin:0 auto;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px))}
.topbar-in{display:flex;align-items:center;gap:12px;height:60px}
.logo{display:flex;align-items:center;gap:10px;font-weight:800;font-size:18px;letter-spacing:-.02em}
.logo-mark{width:34px;height:32px;font-size:14px;letter-spacing:-.03em;border-radius:9px;background:var(--brand);color:var(--brand-ink);display:grid;place-items:center;font-weight:800}
.topbar .spacer{flex:1}
.chip-saldo{display:flex;align-items:center;gap:8px;padding:6px 12px;border-radius:999px;background:var(--surface);border:1px solid var(--line);font-size:13px}
.chip-saldo b{font-family:var(--f-mono);font-weight:600}
.icon-btn{width:40px;height:40px;border-radius:12px;border:1px solid var(--line);background:var(--surface);display:grid;place-items:center;position:relative}
.icon-btn .dot{position:absolute;top:8px;right:9px;width:8px;height:8px;border-radius:50%;background:var(--accent);border:2px solid var(--surface)}
.wrap{padding-block:20px;display:flex;flex-direction:column;gap:20px}

.bnav{position:fixed;left:0;right:0;bottom:0;z-index:30;background:var(--surface);border-top:1px solid var(--line);display:flex;padding:6px max(8px,env(safe-area-inset-right,0px)) calc(6px + env(safe-area-inset-bottom,0px)) max(8px,env(safe-area-inset-left,0px))}
.bnav button{flex:1;border:0;background:none;display:flex;flex-direction:column;align-items:center;gap:2px;padding:6px 0;font-size:11px;font-weight:600;color:var(--muted);border-radius:10px}
.bnav button.on{color:var(--brand)}
.bnav button.on .ico{stroke-width:2.2}

@media (min-width:960px){
  .side{display:flex;flex-direction:column;gap:6px;width:var(--side-w);flex:none;position:sticky;top:0;height:100vh;padding:20px 14px;border-right:1px solid var(--line);background:var(--surface)}
  .side .logo{padding:4px 10px 18px}
  .side nav{display:flex;flex-direction:column;gap:4px}
  .side nav button{display:flex;align-items:center;gap:12px;border:0;background:none;padding:11px 12px;border-radius:11px;font-weight:600;color:var(--muted);text-align:left}
  .side nav button:hover{background:var(--surface-2);color:var(--ink)}
  .side nav button.on{background:var(--brand-soft);color:var(--brand)}
  .side-foot{margin-top:auto;padding:14px;border-radius:12px;background:var(--surface-2);font-size:13px;color:var(--muted)}
  .side-foot b{display:block;color:var(--ink);font-size:14px}
  .bnav,.topbar .logo{display:none}
  .main{padding-bottom:32px}
}

/* ---------- Komponen umum ---------- */
.card{background:var(--surface);border:1px solid var(--line);border-radius:var(--r);padding:18px}
.sec-h{display:flex;align-items:baseline;justify-content:space-between;gap:12px;margin-bottom:12px}
.sec-h h2{font-size:17px;font-weight:700}
.link{border:0;background:none;color:var(--brand);font-weight:700;font-size:13px;padding:0}
.btn{display:inline-flex;align-items:center;justify-content:center;gap:8px;border:0;border-radius:12px;padding:12px 18px;font-weight:700;background:var(--brand);color:var(--brand-ink);transition:transform .08s,filter .15s}
.btn:hover{filter:brightness(1.06)}
.btn:active{transform:scale(.98)}
.btn:disabled{opacity:.45;cursor:not-allowed}
.btn.ghost{background:var(--surface-2);color:var(--ink);border:1px solid var(--line)}
.btn.block{width:100%}
.label{font-size:12px;font-weight:700;letter-spacing:.06em;text-transform:uppercase;color:var(--muted)}
.field{display:flex;flex-direction:column;gap:6px}
.input{width:100%;padding:13px 14px;border-radius:12px;border:1.5px solid var(--line);background:var(--surface-2);outline:none;font-size:16px}
.input:focus{border-color:var(--brand);background:var(--surface)}
.input-wrap{position:relative}
.input-wrap .tag{position:absolute;right:10px;top:50%;transform:translateY(-50%);font-size:12px;font-weight:700;padding:4px 9px;border-radius:999px;background:var(--brand-soft);color:var(--brand)}
.hint{font-size:12.5px;color:var(--muted)}
.pill{display:inline-flex;align-items:center;gap:5px;padding:3px 9px;border-radius:999px;font-size:12px;font-weight:700;white-space:nowrap}
.pill::before{content:"";width:6px;height:6px;border-radius:50%;background:currentColor}
.pill.Sukses{background:var(--ok-soft);color:var(--ok)}
.pill.Pending{background:var(--warn-soft);color:var(--warn)}
.pill.Gagal{background:var(--bad-soft);color:var(--bad)}

/* ---------- Beranda ---------- */
.hello h1{font-size:clamp(20px,3.4vw,26px);font-weight:800;letter-spacing:-.02em}
.hello p{margin:2px 0 0;color:var(--muted)}
.hero{display:grid;gap:16px;grid-template-columns:1fr}
.wallet{border-radius:18px;padding:20px;color:#fff;background:
  radial-gradient(120% 140% at 100% 0%,rgba(255,255,255,.14) 0 30%,transparent 31%),
  repeating-linear-gradient(135deg,rgba(255,255,255,.04) 0 2px,transparent 2px 10px),
  linear-gradient(140deg,var(--hero1),var(--hero2));box-shadow:var(--shadow);display:flex;flex-direction:column;gap:16px}
.wallet .row{display:flex;justify-content:space-between;align-items:flex-start;gap:12px}
.wallet .lbl{font-size:13px;opacity:.82}
.wallet .amt{font-family:var(--f-mono);font-size:clamp(26px,5vw,34px);font-weight:600;letter-spacing:-.03em;line-height:1.1}
.wallet .eye{border:0;background:rgba(255,255,255,.14);color:#fff;width:36px;height:36px;border-radius:10px;display:grid;place-items:center}
.wallet .meta{display:flex;gap:18px;flex-wrap:wrap;font-size:13px}
.wallet .meta b{display:block;font-family:var(--f-mono);font-size:15px}
.wallet .acts{display:grid;grid-template-columns:repeat(4,1fr);gap:8px}
.wallet .acts button{border:0;border-radius:12px;background:rgba(255,255,255,.13);color:#fff;padding:10px 4px;display:flex;flex-direction:column;align-items:center;gap:4px;font-size:12px;font-weight:600}
.wallet .acts button:hover{background:rgba(255,255,255,.22)}
.stats{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.stat{background:var(--surface);border:1px solid var(--line);border-radius:var(--r);padding:14px}
.stat .k{font-size:12.5px;color:var(--muted);font-weight:600}
.stat .v{font-family:var(--f-mono);font-size:19px;font-weight:600;margin-top:2px}
.stat .d{font-size:12px;font-weight:700;color:var(--ok)}
@media (min-width:760px){.hero{grid-template-columns:1.35fr 1fr}.stats{align-content:start}}

.cats{display:grid;grid-template-columns:repeat(4,1fr);gap:10px}
@media (min-width:600px){.cats{grid-template-columns:repeat(5,1fr)}}
.cat{border:1px solid transparent;background:none;border-radius:14px;padding:10px 4px;display:flex;flex-direction:column;align-items:center;gap:7px;font-size:12.5px;font-weight:600;text-align:center;line-height:1.25}
.cat:hover{background:var(--surface-2);border-color:var(--line)}
.cat .badge{width:48px;height:48px;border-radius:14px;display:grid;place-items:center;background:var(--brand-soft);color:var(--brand)}
.cat.alt .badge{background:var(--accent-soft);color:var(--accent)}

.promos{display:grid;grid-auto-flow:column;grid-auto-columns:minmax(250px,1fr);gap:12px;overflow-x:auto;scroll-snap-type:x mandatory;padding-bottom:4px}
.promo{scroll-snap-align:start;border-radius:var(--r);padding:16px;border:1.5px dashed color-mix(in srgb,var(--accent) 55%,transparent);background:var(--accent-soft);display:flex;flex-direction:column;gap:8px}
.promo h3{font-size:15px}
.promo p{margin:0;font-size:13px;color:var(--muted)}
.promo .code{align-self:flex-start;font-family:var(--f-mono);font-size:12.5px;font-weight:600;padding:5px 10px;border-radius:8px;background:var(--surface);border:1px solid var(--line)}

.two{display:grid;gap:20px;grid-template-columns:1fr}
@media (min-width:900px){.two{grid-template-columns:1.4fr 1fr}}
.chart{display:flex;align-items:flex-end;gap:10px;height:150px;padding-top:10px}
.bar{flex:1;display:flex;flex-direction:column;align-items:center;gap:6px;height:100%;justify-content:flex-end}
.bar i{display:block;width:100%;max-width:36px;border-radius:8px 8px 3px 3px;background:var(--brand-soft)}
.bar.now i{background:var(--brand)}
.bar span{font-size:11.5px;color:var(--muted);font-weight:600}
.bar em{font-style:normal;font-family:var(--f-mono);font-size:10.5px;color:var(--muted)}

/* ---------- Daftar transaksi ---------- */
.tx-list{display:flex;flex-direction:column}
.tx{display:flex;align-items:center;gap:12px;padding:12px 0;border-top:1px solid var(--line);border-left:0;border-right:0;border-bottom:0;background:none;text-align:left;width:100%}
.tx:first-child{border-top:0}
.tx .badge{width:42px;height:42px;border-radius:12px;display:grid;place-items:center;background:var(--surface-2);color:var(--brand);flex:none}
.tx .body{flex:1;min-width:0}
.tx .t1{font-weight:700;font-size:14px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.tx .t2{font-size:12.5px;color:var(--muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.tx .r{text-align:right;display:flex;flex-direction:column;align-items:flex-end;gap:4px}
.tx .r .num{font-weight:600;font-size:14px}

/* ---------- Halaman Bayar ---------- */
.tabs{display:flex;gap:8px;overflow-x:auto;padding-bottom:4px;scrollbar-width:none}
.tabs::-webkit-scrollbar{display:none}
.tab{flex:none;border:1px solid var(--line);background:var(--surface);border-radius:999px;padding:8px 14px;font-weight:600;font-size:13.5px;display:flex;align-items:center;gap:7px}
.tab .ico{width:18px;height:18px}
.tab.on{background:var(--ink);color:var(--bg);border-color:var(--ink)}
.pay{display:grid;gap:20px;grid-template-columns:1fr}
@media (min-width:900px){.pay{grid-template-columns:1fr 320px;align-items:start}.summary{position:sticky;top:84px}}
.prods{display:grid;grid-template-columns:repeat(2,1fr);gap:10px}
@media (min-width:600px){.prods{grid-template-columns:repeat(3,1fr)}}
.prod{text-align:left;border:1.5px solid var(--line);background:var(--surface);border-radius:13px;padding:13px;display:flex;flex-direction:column;gap:4px;min-width:0}
.prod:hover{border-color:color-mix(in srgb,var(--brand) 50%,var(--line))}
.prod.on{border-color:var(--brand);background:var(--brand-soft)}
.prod .n{font-weight:700;font-size:14px}
.prod .d{font-size:12px;color:var(--muted)}
.prod .p{font-family:var(--f-mono);font-weight:600;color:var(--brand);font-size:14px;margin-top:4px}
.bill{border-radius:13px;background:var(--surface-2);border:1px solid var(--line);padding:14px;display:flex;flex-direction:column;gap:8px}
.kv{display:flex;justify-content:space-between;gap:12px;font-size:14px}
.kv span:first-child{color:var(--muted)}
.kv span:last-child{text-align:right;font-weight:600;min-width:0;overflow-wrap:anywhere}
.kv.total{border-top:1px dashed var(--line);padding-top:10px;margin-top:4px;font-size:16px}
.kv.total span:last-child{font-family:var(--f-mono);color:var(--brand)}
.empty{text-align:center;color:var(--muted);padding:28px 12px;font-size:14px}

/* ---------- Riwayat ---------- */
.filters{display:flex;flex-wrap:wrap;gap:10px;align-items:center}
.filters .input{max-width:320px;padding:10px 12px;font-size:14px}
.seg{display:flex;background:var(--surface-2);border:1px solid var(--line);border-radius:12px;padding:3px}
.seg button{border:0;background:none;padding:7px 12px;border-radius:9px;font-size:13px;font-weight:600;color:var(--muted)}
.seg button.on{background:var(--surface);color:var(--ink);box-shadow:var(--shadow)}
.table-wrap{overflow-x:auto}
table{width:100%;border-collapse:collapse;font-size:14px}
th{text-align:left;font-size:12px;letter-spacing:.05em;text-transform:uppercase;color:var(--muted);font-weight:700;padding:10px 12px;border-bottom:1px solid var(--line);white-space:nowrap}
td{padding:12px;border-bottom:1px solid var(--line);white-space:nowrap}
tbody tr{cursor:pointer}
tbody tr:hover td{background:var(--surface-2)}
.only-desk{display:none}
@media (min-width:760px){.only-desk{display:block}.only-mob{display:none}}

/* ---------- Deposit & Akun ---------- */
.amounts{display:grid;grid-template-columns:repeat(3,1fr);gap:8px}
.amounts button{border:1.5px solid var(--line);background:var(--surface);border-radius:11px;padding:11px 4px;font-family:var(--f-mono);font-weight:600;font-size:13.5px}
.amounts button.on{border-color:var(--brand);background:var(--brand-soft);color:var(--brand)}
.methods{display:flex;flex-direction:column;gap:8px}
.method{display:flex;align-items:center;gap:12px;border:1.5px solid var(--line);border-radius:12px;padding:12px;background:var(--surface);cursor:pointer}
.method input{accent-color:var(--brand);width:18px;height:18px}
.method .mi{width:40px;height:28px;border-radius:6px;display:grid;place-items:center;font-size:10.5px;font-weight:800;background:var(--surface-2);border:1px solid var(--line);letter-spacing:.03em}
.method .mt{flex:1;font-weight:600;font-size:14px}
.method .mf{font-size:12px;color:var(--muted)}
.method:has(input:checked){border-color:var(--brand);background:var(--brand-soft)}
.profile{display:flex;align-items:center;gap:14px}
.avatar{width:58px;height:58px;border-radius:16px;background:var(--accent);color:#2a1700;display:grid;place-items:center;font-weight:800;font-size:22px;flex:none}
.menu-list{display:flex;flex-direction:column}
.menu-list button{display:flex;align-items:center;gap:12px;padding:14px 4px;border:0;border-top:1px solid var(--line);background:none;text-align:left;font-weight:600}
.menu-list button:first-child{border-top:0}
.menu-list button span{flex:1}
.menu-list .chev{color:var(--muted)}

/* ---------- Modal & toast ---------- */
.overlay{position:fixed;inset:0;z-index:50;background:rgba(6,18,17,.55);display:flex;align-items:flex-end;justify-content:center;animation:fade .15s}
.sheet{background:var(--surface);width:100%;max-width:460px;border-radius:20px 20px 0 0;padding:20px max(18px,env(safe-area-inset-right,0px)) calc(20px + env(safe-area-inset-bottom,0px)) max(18px,env(safe-area-inset-left,0px));max-height:90vh;overflow-y:auto;display:flex;flex-direction:column;gap:14px;animation:up .2s ease-out}
@media (min-width:600px){.overlay{align-items:center}.sheet{border-radius:20px}}
.sheet .grab{width:40px;height:4px;border-radius:4px;background:var(--line);align-self:center}
.sheet h3{font-size:18px}
.receipt{text-align:center;display:flex;flex-direction:column;align-items:center;gap:6px}
.receipt .ok{width:64px;height:64px;border-radius:50%;background:var(--ok-soft);color:var(--ok);display:grid;place-items:center}
.receipt .ok.pend{background:var(--warn-soft);color:var(--warn)}
.receipt .ok.fail{background:var(--bad-soft);color:var(--bad)}
.sn{font-family:var(--f-mono);font-size:15px;font-weight:600;padding:10px 12px;border-radius:10px;background:var(--surface-2);border:1px dashed var(--line);width:100%;word-break:break-all}
.toast{position:fixed;left:50%;bottom:calc(var(--nav-h) + 20px + env(safe-area-inset-bottom,0px));transform:translateX(-50%);z-index:60;background:var(--ink);color:var(--bg);padding:11px 16px;border-radius:12px;font-size:14px;font-weight:600;box-shadow:var(--shadow);max-width:calc(100% - 32px);animation:up .2s}
@media (min-width:960px){.toast{bottom:28px}}
@keyframes fade{from{opacity:0}}
@keyframes up{from{transform:translateY(16px);opacity:0}}
.toast{transform:translateX(-50%)}
@media (prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}}
.view{display:flex;flex-direction:column;gap:20px}

/* ---------- Login ---------- */
.auth{min-height:100vh;display:grid;grid-template-columns:1fr;background:var(--bg)}
.auth-brand{color:#fff;background:
  radial-gradient(90% 70% at 100% 0%,rgba(255,255,255,.12) 0 35%,transparent 36%),
  repeating-linear-gradient(135deg,rgba(255,255,255,.035) 0 2px,transparent 2px 12px),
  linear-gradient(150deg,var(--hero1),var(--hero2));
  padding-block:28px 64px;padding-left:max(20px,env(safe-area-inset-left,0px));padding-right:max(20px,env(safe-area-inset-right,0px));
  display:flex;flex-direction:column;gap:18px}
.auth-brand .logo-mark{background:#fff;color:var(--hero2)}
.auth-brand .tagline{font-size:clamp(22px,4.5vw,40px);font-weight:800;letter-spacing:-.03em;line-height:1.12;max-width:16ch}
.auth-brand .sub{margin:0;opacity:.85;max-width:44ch}
.svc{display:flex;flex-wrap:wrap;gap:8px}
.svc span{display:inline-flex;align-items:center;gap:6px;padding:6px 11px;border-radius:999px;background:rgba(255,255,255,.12);font-size:13px;font-weight:600}
.svc .ico{width:16px;height:16px}
.slip{display:none;background:#fff;color:#10292b;border-radius:14px;padding:16px 18px;max-width:340px;box-shadow:0 18px 40px -16px rgba(0,0,0,.45);transform:rotate(-2deg);font-size:13px}
.slip .h{display:flex;justify-content:space-between;font-weight:800;margin-bottom:8px}
.slip .row{display:flex;justify-content:space-between;gap:10px;color:#5d7472;padding:2px 0}
.slip .row b{color:#10292b;font-family:var(--f-mono);font-weight:600}
.slip .tok{margin-top:10px;padding:9px;border:1px dashed #b9cbc6;border-radius:8px;font-family:var(--f-mono);font-weight:600;text-align:center;letter-spacing:.02em}
.auth-brand .foot{margin-top:auto;font-size:12.5px;opacity:.7}
.auth-form{display:flex;justify-content:center;align-items:flex-start;padding-block:0 32px;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px))}
.login-card{width:100%;max-width:420px;margin-top:-40px;background:var(--surface);border:1px solid var(--line);border-radius:20px;padding:26px 22px;box-shadow:var(--shadow);display:flex;flex-direction:column;gap:16px}
.login-card h2{font-size:22px;font-weight:800;letter-spacing:-.02em}
.login-card .lead{margin:-10px 0 0;color:var(--muted);font-size:14px}
.pw{position:relative}
.pw .input{padding-right:48px}
.pw button{position:absolute;right:6px;top:50%;transform:translateY(-50%);width:38px;height:38px;border:0;background:none;color:var(--muted);display:grid;place-items:center;border-radius:9px}
.row-between{display:flex;justify-content:space-between;align-items:center;gap:10px;flex-wrap:wrap;font-size:13.5px}
.check{display:flex;align-items:center;gap:8px;cursor:pointer}
.check input{accent-color:var(--brand);width:17px;height:17px}
.alert{display:flex;gap:10px;align-items:flex-start;padding:11px 12px;border-radius:11px;background:var(--bad-soft);color:var(--bad);font-size:13.5px;font-weight:600}
.alert .ico{width:18px;height:18px;margin-top:1px}
.demo{border:1px dashed var(--line);border-radius:12px;padding:12px;display:flex;justify-content:space-between;align-items:center;gap:10px;background:var(--surface-2);font-size:13px}
.demo .num{font-size:12.5px}
.demo .k{color:var(--muted)}
.input.err{border-color:var(--bad)}
.spin{width:18px;height:18px;border-radius:50%;border:2.5px solid currentColor;border-right-color:transparent;animation:rot .7s linear infinite}
@keyframes rot{to{transform:rotate(360deg)}}
@keyframes shake{20%,60%{transform:translateX(-6px)}40%,80%{transform:translateX(6px)}}
.shake{animation:shake .35s}
@media (min-width:900px){
  .auth{grid-template-columns:1.05fr 1fr}
  .auth-brand{min-height:100vh;padding:48px 56px;gap:24px;justify-content:center}
  .slip{display:block}
  .auth-form{align-items:center;padding:40px}
  .login-card{margin-top:0;padding:34px 32px}
}
</style>
</head>
<body>
<svg width="0" height="0" style="position:absolute" aria-hidden="true">
  <defs>
    <symbol id="i-home" viewBox="0 0 24 24"><path d="M3 10.5 12 3l9 7.5V20a1 1 0 0 1-1 1h-5v-6h-6v6H4a1 1 0 0 1-1-1z"/></symbol>
    <symbol id="i-grid" viewBox="0 0 24 24"><rect x="3" y="3" width="7" height="7" rx="2"/><rect x="14" y="3" width="7" height="7" rx="2"/><rect x="3" y="14" width="7" height="7" rx="2"/><rect x="14" y="14" width="7" height="7" rx="2"/></symbol>
    <symbol id="i-clock" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M12 7v5l3 2"/></symbol>
    <symbol id="i-user" viewBox="0 0 24 24"><circle cx="12" cy="8" r="4"/><path d="M4 21c0-4 3.6-7 8-7s8 3 8 7"/></symbol>
    <symbol id="i-plus" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></symbol>
    <symbol id="i-wallet" viewBox="0 0 24 24"><path d="M3 7a2 2 0 0 1 2-2h13v4"/><rect x="3" y="7" width="18" height="13" rx="2"/><path d="M16 13.5h2"/></symbol>
    <symbol id="i-send" viewBox="0 0 24 24"><path d="M5 12h14M13 6l6 6-6 6"/></symbol>
    <symbol id="i-qr" viewBox="0 0 24 24"><rect x="3" y="3" width="7" height="7"/><rect x="14" y="3" width="7" height="7"/><rect x="3" y="14" width="7" height="7"/><path d="M14 14h3v3M21 14v7h-4M17 21v-2"/></symbol>
    <symbol id="i-bell" viewBox="0 0 24 24"><path d="M6 16V11a6 6 0 1 1 12 0v5l2 2H4z"/><path d="M10 21h4"/></symbol>
    <symbol id="i-eye" viewBox="0 0 24 24"><path d="M2 12s3.6-7 10-7 10 7 10 7-3.6 7-10 7S2 12 2 12z"/><circle cx="12" cy="12" r="3"/></symbol>
    <symbol id="i-eyeoff" viewBox="0 0 24 24"><path d="M3 3l18 18M10.6 6.1A10 10 0 0 1 12 6c6.4 0 10 6 10 6a17 17 0 0 1-3.2 3.8M6.2 7.6C3.6 9.4 2 12 2 12s3.6 7 10 7a9.6 9.6 0 0 0 4.3-1"/></symbol>
    <symbol id="i-pulsa" viewBox="0 0 24 24"><rect x="6" y="2" width="12" height="20" rx="3"/><path d="M11 18h2"/></symbol>
    <symbol id="i-data" viewBox="0 0 24 24"><path d="M2 9a15 15 0 0 1 20 0M5.5 12.5a10 10 0 0 1 13 0M9 16a5 5 0 0 1 6 0"/><circle cx="12" cy="19.5" r="1"/></symbol>
    <symbol id="i-pln" viewBox="0 0 24 24"><path d="M13 2 4 14h7l-1 8 9-12h-7z"/></symbol>
    <symbol id="i-plnpasca" viewBox="0 0 24 24"><rect x="4" y="3" width="16" height="18" rx="2"/><path d="m13 7-3 5h4l-3 5"/></symbol>
    <symbol id="i-pdam" viewBox="0 0 24 24"><path d="M12 3s6 6.5 6 11a6 6 0 0 1-12 0c0-4.5 6-11 6-11z"/></symbol>
    <symbol id="i-bpjs" viewBox="0 0 24 24"><path d="M12 21s-8-4.5-8-11a5 5 0 0 1 8-4 5 5 0 0 1 8 4c0 6.5-8 11-8 11z"/><path d="M12 9v6M9 12h6"/></symbol>
    <symbol id="i-ewallet" viewBox="0 0 24 24"><rect x="2" y="6" width="20" height="14" rx="3"/><path d="M2 10h20M6 15h4"/></symbol>
    <symbol id="i-game" viewBox="0 0 24 24"><path d="M6 8h12a4 4 0 0 1 4 4v2a3 3 0 0 1-5.4 1.8L15 14H9l-1.6 1.8A3 3 0 0 1 2 14v-2a4 4 0 0 1 4-4z"/><path d="M7 11v3M5.5 12.5h3"/><circle cx="16" cy="11.5" r=".6"/><circle cx="18" cy="13" r=".6"/></symbol>
    <symbol id="i-tv" viewBox="0 0 24 24"><rect x="2" y="6" width="20" height="13" rx="2"/><path d="m8 2 4 4 4-4"/></symbol>
    <symbol id="i-internet" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M3 12h18M12 3a14 14 0 0 1 0 18M12 3a14 14 0 0 0 0 18"/></symbol>
    <symbol id="i-check" viewBox="0 0 24 24"><path d="m5 12 5 5L20 7"/></symbol>
    <symbol id="i-x" viewBox="0 0 24 24"><path d="M6 6l12 12M18 6 6 18"/></symbol>
    <symbol id="i-hour" viewBox="0 0 24 24"><path d="M7 3h10M7 21h10M8 3c0 5 8 5 8 9s-8 4-8 9M16 3c0 5-8 5-8 9"/></symbol>
    <symbol id="i-chev" viewBox="0 0 24 24"><path d="m9 6 6 6-6 6"/></symbol>
    <symbol id="i-search" viewBox="0 0 24 24"><circle cx="11" cy="11" r="7"/><path d="m20 20-4-4"/></symbol>
    <symbol id="i-gift" viewBox="0 0 24 24"><rect x="3" y="8" width="18" height="5" rx="1"/><path d="M5 13v8h14v-8M12 8v13M12 8S10.5 3 8 4s1 4 4 4c3 0 6.5-3 4-4s-4 4-4 4"/></symbol>
    <symbol id="i-shield" viewBox="0 0 24 24"><path d="M12 3 4 6v6c0 5 3.5 8 8 9 4.5-1 8-4 8-9V6z"/><path d="m9 12 2 2 4-4"/></symbol>
    <symbol id="i-help" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M9.5 9.5a2.5 2.5 0 1 1 3.5 2.3c-.6.3-1 .9-1 1.5V14M12 17.5v.01"/></symbol>
    <symbol id="i-logout" viewBox="0 0 24 24"><path d="M15 4h4a1 1 0 0 1 1 1v14a1 1 0 0 1-1 1h-4M10 17l5-5-5-5M15 12H3"/></symbol>
    <symbol id="i-moon" viewBox="0 0 24 24"><path d="M20 14.5A8 8 0 0 1 9.5 4a8 8 0 1 0 10.5 10.5z"/></symbol>
    <symbol id="i-mail" viewBox="0 0 24 24"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="m4 7 8 6 8-6"/></symbol>
    <symbol id="i-alert" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M12 7.5v5M12 16.5v.01"/></symbol>
  </defs>
</svg>

<?php if ($showLogin): ?>
<!-- ============ HALAMAN LOGIN ============ -->
<div class="auth" id="loginScreen">
  <section class="auth-brand">
    <div class="logo"><span class="logo-mark">FB</span>Feri Bayarin</div>
    <h1 class="tagline">Satu loket untuk semua tagihan dan produk digital.</h1>
    <p class="sub">Masuk ke dashboard agen untuk jual pulsa, token listrik, dan bayar tagihan pelanggan.</p>
    <div class="svc">
      <span><svg class="ico"><use href="#i-pulsa"/></svg>Pulsa</span>
      <span><svg class="ico"><use href="#i-pln"/></svg>Token PLN</span>
      <span><svg class="ico"><use href="#i-pdam"/></svg>PDAM</span>
      <span><svg class="ico"><use href="#i-bpjs"/></svg>BPJS</span>
      <span><svg class="ico"><use href="#i-ewallet"/></svg>E-Wallet</span>
      <span><svg class="ico"><use href="#i-game"/></svg>Game</span>
    </div>
    <div class="slip" aria-hidden="true">
      <div class="h"><span>STRUK TOKEN PLN</span><span style="color:#1a8a4a">SUKSES</span></div>
      <div class="row"><span>ID Pelanggan</span><b>532110987654</b></div>
      <div class="row"><span>Tarif/Daya</span><b>R1/1300VA</b></div>
      <div class="row"><span>Nominal</span><b>Rp100.000</b></div>
      <div class="row"><span>kWh</span><b>65,6</b></div>
      <div class="tok">4821-0937-1166-2254-8790</div>
    </div>
    <div class="foot">© <?= date('Y') ?> Feri Bayarin PPOB · Data demo</div>
  </section>

  <section class="auth-form">
    <form class="login-card" id="loginForm" method="post" action="" novalidate>
      <div>
        <h2>Masuk ke akun</h2>
      </div>
      <p class="lead">Gunakan email dan password akun agen kamu.</p>

      <div class="alert" id="loginErr" role="alert" <?= $loginError ? '' : 'hidden' ?>>
        <svg class="ico"><use href="#i-alert"/></svg><span id="loginErrText"><?= $h($loginError) ?></span>
      </div>

      <input type="hidden" name="action" value="login">
      <input type="hidden" name="csrf" value="<?= $preview ? '' : $h($_SESSION['csrf']) ?>">

      <div class="field">
        <label class="label" for="email">Email</label>
        <input class="input" id="email" name="email" type="email" inputmode="email" autocomplete="username" placeholder="nama@email.com" value="<?= $h($oldEmail) ?>" required>
      </div>
      <div class="field">
        <label class="label" for="password">Password</label>
        <div class="pw">
          <input class="input" id="password" name="password" type="password" autocomplete="current-password" placeholder="Masukkan password" required>
          <button type="button" id="pwToggle" aria-label="Tampilkan password"><svg class="ico"><use href="#i-eye"/></svg></button>
        </div>
      </div>

      <div class="row-between">
        <label class="check"><input type="checkbox" id="remember" name="remember" checked>Ingat saya</label>
        <button type="button" class="link" id="forgotBtn">Lupa password?</button>
      </div>

      <button class="btn block" type="submit" id="loginBtn">Masuk</button>

      <div class="demo">
        <div><div class="k">Akun demo</div><div class="num">admin@admin.com · 123456</div></div>
        <button type="button" class="btn ghost" id="fillDemo" style="padding:8px 12px;font-size:13px">Isi otomatis</button>
      </div>
    </form>
  </section>
</div>
<?php endif; ?>

<?php if ($showApp): ?>
<div id="appShell" <?= $authed ? '' : 'hidden' ?>>
<div class="app">
  <!-- Sidebar (desktop) -->
  <aside class="side" aria-label="Navigasi utama">
    <div class="logo"><span class="logo-mark">FB</span>Feri Bayarin</div>
    <nav id="sideNav">
      <button data-go="home" class="on"><svg class="ico"><use href="#i-home"/></svg>Beranda</button>
      <button data-go="pay"><svg class="ico"><use href="#i-grid"/></svg>Bayar &amp; Beli</button>
      <button data-go="history"><svg class="ico"><use href="#i-clock"/></svg>Riwayat</button>
      <button data-go="deposit"><svg class="ico"><use href="#i-plus"/></svg>Isi Saldo</button>
      <button data-go="account"><svg class="ico"><use href="#i-user"/></svg>Akun</button>
    </nav>
    <div class="side-foot"><b><?= htmlspecialchars($user['level']) ?></b>ID Agen <span class="num"><?= $user['id'] ?></span></div>
  </aside>

  <div class="main">
    <header class="topbar">
      <div class="topbar-in">
        <div class="logo"><span class="logo-mark">FB</span>Feri Bayarin</div>
        <div class="spacer"></div>
        <div class="chip-saldo"><svg class="ico" style="width:18px;height:18px"><use href="#i-wallet"/></svg><b id="topSaldo"><?= rupiah($user['saldo']) ?></b></div>
        <button class="icon-btn" id="themeBtn" aria-label="Ganti tema"><svg class="ico"><use href="#i-moon"/></svg></button>
        <button class="icon-btn" aria-label="Notifikasi" data-toast="3 notifikasi baru: promo PLN, transaksi sukses, poin bertambah"><svg class="ico"><use href="#i-bell"/></svg><span class="dot"></span></button>
      </div>
    </header>

    <main class="wrap" id="root">
      <!-- ============ BERANDA ============ -->
      <section class="view" data-view="home">
        <div class="hello">
          <h1><?= $greet ?>, <?= htmlspecialchars($firstName) ?></h1>
          <p>Bayar tagihan dan beli produk digital dalam satu tempat.</p>
        </div>

        <div class="hero">
          <div class="wallet">
            <div class="row">
              <div>
                <div class="lbl">Saldo Feri Bayarin</div>
                <div class="amt" id="walletAmt"><?= rupiah($user['saldo']) ?></div>
              </div>
              <button class="eye" id="eyeBtn" aria-label="Sembunyikan saldo"><svg class="ico"><use href="#i-eye"/></svg></button>
            </div>
            <div class="meta">
              <div>Poin<b id="poinVal"><?= number_format($user['poin'], 0, ',', '.') ?></b></div>
              <div>Level<b style="font-family:var(--f-body)"><?= htmlspecialchars($user['level']) ?></b></div>
            </div>
            <div class="acts">
              <button data-go="deposit"><svg class="ico"><use href="#i-plus"/></svg>Isi Saldo</button>
              <button data-toast="Fitur transfer saldo antar agen (demo)"><svg class="ico"><use href="#i-send"/></svg>Transfer</button>
              <button data-toast="Pindai QRIS (demo)"><svg class="ico"><use href="#i-qr"/></svg>Scan</button>
              <button data-go="history"><svg class="ico"><use href="#i-clock"/></svg>Riwayat</button>
            </div>
          </div>
          <div class="stats" id="stats"></div>
        </div>

        <div class="card">
          <div class="sec-h"><h2>Layanan</h2><button class="link" data-go="pay">Lihat semua</button></div>
          <div class="cats" id="homeCats"></div>
        </div>

        <div>
          <div class="sec-h"><h2>Promo untuk kamu</h2></div>
          <div class="promos" id="promos"></div>
        </div>

        <div class="two">
          <div class="card">
            <div class="sec-h"><h2>Transaksi terakhir</h2><button class="link" data-go="history">Semua</button></div>
            <div class="tx-list" id="recentTx"></div>
          </div>
          <div class="card">
            <div class="sec-h"><h2>Pengeluaran 6 bulan</h2><span class="hint">dalam ribu Rp</span></div>
            <div class="chart" id="chart" role="img" aria-label="Grafik pengeluaran bulanan"></div>
          </div>
        </div>
      </section>

      <!-- ============ BAYAR ============ -->
      <section class="view" data-view="pay" hidden>
        <div class="hello"><h1>Bayar &amp; Beli</h1><p>Pilih layanan, isi nomor tujuan, lalu pilih nominal.</p></div>
        <div class="tabs" id="payTabs" role="tablist"></div>
        <div class="pay">
          <div class="card" style="display:flex;flex-direction:column;gap:16px">
            <div class="field">
              <label class="label" for="target" id="targetLbl">Nomor HP</label>
              <div class="input-wrap">
                <input class="input num" id="target" inputmode="numeric" autocomplete="off" placeholder="0812xxxxxxxx">
                <span class="tag" id="opTag" hidden></span>
              </div>
              <span class="hint" id="targetHint">Contoh nomor dummy: 081234567890</span>
            </div>
            <div id="prodArea"></div>
          </div>
          <aside class="card summary" id="summary"></aside>
        </div>
      </section>

      <!-- ============ RIWAYAT ============ -->
      <section class="view" data-view="history" hidden>
        <div class="hello"><h1>Riwayat Transaksi</h1><p>Ketuk transaksi untuk melihat struk dan nomor SN.</p></div>
        <div class="filters">
          <div class="input-wrap" style="flex:1;min-width:200px;max-width:340px">
            <input class="input" id="q" placeholder="Cari produk, nomor, atau ID…" style="max-width:none;padding-left:38px">
            <svg class="ico" style="position:absolute;left:11px;top:50%;transform:translateY(-50%);width:18px;height:18px;color:var(--muted)"><use href="#i-search"/></svg>
          </div>
          <div class="seg" id="statusSeg">
            <button class="on" data-s="Semua">Semua</button><button data-s="Sukses">Sukses</button><button data-s="Pending">Pending</button><button data-s="Gagal">Gagal</button>
          </div>
        </div>
        <div class="card only-desk" style="padding:6px">
          <div class="table-wrap">
            <table>
              <thead><tr><th>Waktu</th><th>ID Transaksi</th><th>Produk</th><th>Tujuan</th><th style="text-align:right">Nominal</th><th>Status</th></tr></thead>
              <tbody id="histTable"></tbody>
            </table>
          </div>
        </div>
        <div class="card only-mob"><div class="tx-list" id="histList"></div></div>
      </section>

      <!-- ============ DEPOSIT ============ -->
      <section class="view" data-view="deposit" hidden>
        <div class="hello"><h1>Isi Saldo</h1><p>Saldo masuk otomatis setelah pembayaran terkonfirmasi.</p></div>
        <div class="pay">
          <div class="card" style="display:flex;flex-direction:column;gap:18px">
            <div class="field">
              <label class="label" for="depAmt">Nominal deposit</label>
              <input class="input num" id="depAmt" inputmode="numeric" placeholder="Min. Rp10.000" value="100.000">
              <div class="amounts" id="depChips"></div>
            </div>
            <div class="field">
              <span class="label">Metode pembayaran</span>
              <div class="methods" id="methods"></div>
            </div>
          </div>
          <aside class="card summary" id="depSummary"></aside>
        </div>
      </section>

      <!-- ============ AKUN ============ -->
      <section class="view" data-view="account" hidden>
        <div class="card profile">
          <div class="avatar"><?= strtoupper(substr($user['name'], 0, 1)) ?></div>
          <div style="min-width:0">
            <h1 style="font-size:20px"><?= htmlspecialchars($user['name']) ?></h1>
            <div class="hint"><?= htmlspecialchars($user['email']) ?> · <span class="num"><?= $user['phone'] ?></span></div>
            <div style="margin-top:6px"><span class="pill Sukses"><?= htmlspecialchars($user['level']) ?></span></div>
          </div>
        </div>
        <div class="two">
          <div class="card">
            <div class="sec-h"><h2>Detail akun</h2></div>
            <div class="bill" style="background:none;border:0;padding:0">
              <div class="kv"><span>ID Agen</span><span class="num"><?= $user['id'] ?></span></div>
              <div class="kv"><span>Bergabung</span><span><?= $user['joined'] ?></span></div>
              <div class="kv"><span>Total transaksi</span><span id="accCount">-</span></div>
              <div class="kv"><span>Poin</span><span class="num" id="accPoin">-</span></div>
            </div>
          </div>
          <div class="card">
            <div class="menu-list">
              <button data-toast="Undang teman, dapat 500 poin (demo)"><svg class="ico"><use href="#i-gift"/></svg><span>Undang teman</span><svg class="ico chev"><use href="#i-chev"/></svg></button>
              <button data-toast="Ubah PIN transaksi (demo)"><svg class="ico"><use href="#i-shield"/></svg><span>Keamanan &amp; PIN</span><svg class="ico chev"><use href="#i-chev"/></svg></button>
              <button data-toast="CS Feri Bayarin: 24 jam via chat (demo)"><svg class="ico"><use href="#i-help"/></svg><span>Pusat bantuan</span><svg class="ico chev"><use href="#i-chev"/></svg></button>
              <button id="logoutBtn"><svg class="ico"><use href="#i-logout"/></svg><span>Keluar</span><svg class="ico chev"><use href="#i-chev"/></svg></button>
            </div>
          </div>
        </div>
        <p class="hint" style="text-align:center">Feri Bayarin PPOB · versi demo dengan data dummy · <?= date('d M Y') ?></p>
      </section>
    </main>
  </div>
</div>

<!-- Bottom nav (mobile/tablet) -->
<nav class="bnav" id="bNav" aria-label="Navigasi bawah">
  <button data-go="home" class="on"><svg class="ico"><use href="#i-home"/></svg>Beranda</button>
  <button data-go="pay"><svg class="ico"><use href="#i-grid"/></svg>Bayar</button>
  <button data-go="deposit"><svg class="ico"><use href="#i-plus"/></svg>Isi Saldo</button>
  <button data-go="history"><svg class="ico"><use href="#i-clock"/></svg>Riwayat</button>
  <button data-go="account"><svg class="ico"><use href="#i-user"/></svg>Akun</button>
</nav>
</div><!-- /#appShell -->
<?php endif; ?>

<div id="modal" hidden></div>
<div class="toast" id="toast" hidden></div>

<?php if ($showLogin): ?>
<script>
/* ---------- Login ---------- */
(function(){
  "use strict";
  const PREVIEW = <?= $preview ? 'true' : 'false' ?>; // true = pratinjau statis, login dicek di browser
  const DEMO = { email: "admin@admin.com", pass: "123456" };
  const f = document.getElementById("loginForm"), em = document.getElementById("email"), pw = document.getElementById("password");
  const err = document.getElementById("loginErr"), errT = document.getElementById("loginErrText"), btn = document.getElementById("loginBtn");
  const t = document.getElementById("toast"); let tt;
  const toast = m => { t.textContent = m; t.hidden = false; clearTimeout(tt); tt = setTimeout(() => t.hidden = true, 2600); };
  const showErr = m => { errT.textContent = m; err.hidden = false; f.classList.remove("shake"); void f.offsetWidth; f.classList.add("shake"); };
  const busy = on => { btn.disabled = on; btn.innerHTML = on ? '<span class="spin"></span>Memeriksa…' : "Masuk"; };

  try { const r = localStorage.getItem("fb-remember"); if (r && !em.value) em.value = r; } catch(e) {}

  document.getElementById("pwToggle").onclick = function(){
    const show = pw.type === "password"; pw.type = show ? "text" : "password";
    this.innerHTML = `<svg class="ico"><use href="#i-${show ? "eyeoff" : "eye"}"/></svg>`;
    this.setAttribute("aria-label", show ? "Sembunyikan password" : "Tampilkan password");
  };
  document.getElementById("fillDemo").onclick = () => { em.value = DEMO.email; pw.value = DEMO.pass; err.hidden = true; em.classList.remove("err"); pw.classList.remove("err"); btn.focus(); };
  document.getElementById("forgotBtn").onclick = () => toast("Link reset password dikirim ke email (demo)");
  [em, pw].forEach(i => i.addEventListener("input", () => { i.classList.remove("err"); err.hidden = true; }));

  function enterApp(){
    try { document.getElementById("remember").checked ? localStorage.setItem("fb-remember", em.value.trim()) : localStorage.removeItem("fb-remember"); } catch(e) {}
    if (!PREVIEW) { location.reload(); return; }
    document.getElementById("loginScreen").hidden = true;
    document.getElementById("appShell").hidden = false;
    window.scrollTo(0, 0);
    toast("Selamat datang, Admin Feri");
  }

  f.addEventListener("submit", e => {
    e.preventDefault();
    const email = em.value.trim().toLowerCase(), pass = pw.value;
    em.classList.toggle("err", !email); pw.classList.toggle("err", !pass);
    if (!email || !pass) { showErr("Email dan password wajib diisi."); return; }
    if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) { em.classList.add("err"); showErr("Format email belum benar."); return; }
    busy(true);
    if (PREVIEW) {
      setTimeout(() => {
        busy(false);
        if (email === DEMO.email && pass === DEMO.pass) enterApp();
        else { pw.value = ""; pw.classList.add("err"); showErr("Email atau password salah."); }
      }, 700);
      return;
    }
    fetch(location.pathname, { method: "POST", body: new FormData(f), headers: { "X-Requested-With": "fetch" }, credentials: "same-origin" })
      .then(r => r.json())
      .then(j => { if (j.ok) enterApp(); else { busy(false); pw.value = ""; pw.classList.add("err"); showErr(j.error || "Login gagal."); } })
      .catch(() => f.submit()); // fallback: kirim form biasa
  });

  // Dipakai tombol "Keluar" di mode pratinjau
  window.__fbLogout = () => {
    document.getElementById("appShell").hidden = true;
    document.getElementById("loginScreen").hidden = false;
    pw.value = ""; err.hidden = true; window.scrollTo(0, 0);
    toast("Kamu sudah keluar");
  };
})();
</script>
<?php endif; ?>

<?php if ($showApp): ?>
<script>
const DATA = <?= $appData ?>;
(function(){
  "use strict";
  const $ = (s, el=document) => el.querySelector(s);
  const $$ = (s, el=document) => [...el.querySelectorAll(s)];
  const rp = n => "Rp" + Math.round(n).toLocaleString("id-ID");
  const esc = s => String(s).replace(/[&<>"']/g, c => ({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
  const ico = (id, cls="ico") => `<svg class="${cls}"><use href="#i-${id}"/></svg>`;

  const state = {
    saldo: DATA.user.saldo, poin: DATA.user.poin, hide: false,
    tx: DATA.transactions.slice(), cat: "pulsa", product: null, bill: null,
    filter: "Semua", q: "", depAmt: 100000, depMethod: "bca"
  };
  const catOf = k => DATA.categories.find(c => c.key === k);

  /* ---------- Operator detection ---------- */
  const OPS = [
    ["Telkomsel", ["0811","0812","0813","0821","0822","0823","0851","0852","0853"]],
    ["Indosat",   ["0814","0815","0816","0855","0856","0857","0858"]],
    ["XL",        ["0817","0818","0819","0859","0877","0878"]],
    ["Axis",      ["0831","0832","0833","0838"]],
    ["Tri",       ["0895","0896","0897","0898","0899"]],
    ["Smartfren", ["0881","0882","0883","0884","0885","0886","0887","0888","0889"]],
  ];
  const detectOp = n => { const p = n.replace(/\D/g,"").replace(/^62/,"0").slice(0,4); const f = OPS.find(o => o[1].includes(p)); return f ? f[0] : null; };

  /* ---------- Navigation ---------- */
  function go(view){
    $$(".view").forEach(v => v.hidden = v.dataset.view !== view);
    $$("[data-go]").forEach(b => { if (b.closest("#sideNav,#bNav")) b.classList.toggle("on", b.dataset.go === view); });
    window.scrollTo({top:0, behavior:"smooth"});
    try { history.replaceState(null, "", "#" + view); } catch(e) {}
  }
  document.addEventListener("click", e => {
    const g = e.target.closest("[data-go]"); if (g) { go(g.dataset.go); return; }
    const t = e.target.closest("[data-toast]"); if (t) toast(t.dataset.toast);
  });

  /* ---------- Toast ---------- */
  let tT;
  function toast(msg){ const t = $("#toast"); t.textContent = msg; t.hidden = false; clearTimeout(tT); tT = setTimeout(() => t.hidden = true, 2600); }

  /* ---------- Saldo ---------- */
  function renderSaldo(){
    const s = state.hide ? "Rp ••••••" : rp(state.saldo);
    $("#walletAmt").textContent = s; $("#topSaldo").textContent = s;
    $("#poinVal").textContent = state.poin.toLocaleString("id-ID");
    $("#eyeBtn").innerHTML = ico(state.hide ? "eyeoff" : "eye");
    $("#accPoin").textContent = state.poin.toLocaleString("id-ID");
    $("#accCount").textContent = state.tx.length + " transaksi";
  }
  $("#eyeBtn").onclick = () => { state.hide = !state.hide; renderSaldo(); };

  /* ---------- Beranda ---------- */
  function renderStats(){
    const ok = state.tx.filter(t => t.status === "Sukses");
    const month = ok.reduce((a,t) => a + t.amount, 0);
    const pend = state.tx.filter(t => t.status === "Pending").length;
    $("#stats").innerHTML = [
      ["Belanja Oktober", rp(month), "+39% dari Sep"],
      ["Transaksi sukses", ok.length + "", "dari " + state.tx.length + " total"],
      ["Menunggu proses", pend + "", pend ? "cek riwayat" : "semua selesai"],
      ["Estimasi komisi", rp(month * 0.012), "1,2% per transaksi"],
    ].map(([k,v,d]) => `<div class="stat"><div class="k">${k}</div><div class="v">${v}</div><div class="d">${d}</div></div>`).join("");
  }
  function renderHome(){
    $("#homeCats").innerHTML = DATA.categories.map((c,i) =>
      `<button class="cat${c.type==='postpaid'?' alt':''}" data-cat="${c.key}"><span class="badge">${ico(c.key)}</span>${esc(c.name)}</button>`).join("");
    $$("#homeCats .cat").forEach(b => b.onclick = () => { selectCat(b.dataset.cat); go("pay"); });
    $("#promos").innerHTML = DATA.promos.map(p =>
      `<div class="promo"><h3>${esc(p.title)}</h3><p>${esc(p.sub)}</p><button class="code" data-copy="${p.code}">${p.code} · Salin</button></div>`).join("");
    $$("[data-copy]").forEach(b => b.onclick = () => {
      const c = b.dataset.copy;
      (navigator.clipboard ? navigator.clipboard.writeText(c) : Promise.reject()).then(() => toast("Kode " + c + " disalin"), () => toast("Kode promo: " + c));
    });
    const max = Math.max(...DATA.spending.map(s => s.v));
    $("#chart").innerHTML = DATA.spending.map((s,i,a) =>
      `<div class="bar${i===a.length-1?' now':''}"><em>${Math.round(s.v/1000).toLocaleString("id-ID")}</em><i style="height:${(s.v/max*100).toFixed(1)}%"></i><span>${s.m}</span></div>`).join("");
    renderStats(); renderRecent();
  }
  const txRow = t => `<button class="tx" data-tx="${t.id}"><span class="badge">${ico(t.cat)}</span>
      <span class="body"><span class="t1" style="display:block">${esc(t.product)}</span><span class="t2" style="display:block"><span class="num">${esc(t.target)}</span> · ${t.date.slice(5).replace("-","/")}</span></span>
      <span class="r"><span class="num">${rp(t.amount)}</span><span class="pill ${t.status}">${t.status}</span></span></button>`;
  function renderRecent(){ $("#recentTx").innerHTML = state.tx.slice(0,5).map(txRow).join(""); bindTx($("#recentTx")); }
  function bindTx(el){ $$("[data-tx]", el).forEach(b => b.onclick = () => showReceipt(state.tx.find(t => t.id === b.dataset.tx))); }

  /* ---------- Bayar ---------- */
  function renderTabs(){
    $("#payTabs").innerHTML = DATA.categories.map(c =>
      `<button class="tab${c.key===state.cat?' on':''}" role="tab" aria-selected="${c.key===state.cat}" data-tab="${c.key}">${ico(c.key)}${esc(c.name)}</button>`).join("");
    $$("#payTabs .tab").forEach(b => b.onclick = () => selectCat(b.dataset.tab));
  }
  function selectCat(k){
    state.cat = k; state.product = null; state.bill = null;
    const c = catOf(k);
    $("#targetLbl").textContent = c.input;
    $("#target").placeholder = c.ph;
    $("#target").value = "";
    $("#targetHint").textContent = c.type === "postpaid" ? "Masukkan nomor lalu tekan Cek Tagihan. Nomor apa pun akan menghasilkan tagihan dummy." : "Contoh nomor dummy: " + c.ph.replace(/x/g, "7");
    renderTabs(); renderProducts(); renderSummary(); updateOp();
    const t = $(`#payTabs [data-tab="${k}"]`); if (t) t.scrollIntoView({block:"nearest", inline:"center"});
  }
  function updateOp(){
    const tag = $("#opTag"), v = $("#target").value;
    if (["pulsa","data"].includes(state.cat) && v.length >= 4){ const op = detectOp(v); tag.hidden = !op; tag.textContent = op || ""; }
    else tag.hidden = true;
  }
  $("#target").addEventListener("input", e => {
    if (state.cat !== "game") e.target.value = e.target.value.replace(/[^\d]/g, "").slice(0, 16);
    state.bill = null; updateOp(); if (catOf(state.cat).type === "postpaid") renderProducts(); renderSummary();
  });
  function renderProducts(){
    const c = catOf(state.cat), area = $("#prodArea");
    if (c.type === "postpaid"){
      area.innerHTML = state.bill
        ? `<div class="bill">
            <div class="kv"><span>Nama</span><span>${esc(state.bill.name)}</span></div>
            <div class="kv"><span>Periode</span><span>${esc(state.bill.period)}</span></div>
            ${state.bill.extra.map(([k,v]) => `<div class="kv"><span>${k}</span><span>${esc(v)}</span></div>`).join("")}
            <div class="kv"><span>Tagihan</span><span class="num">${rp(state.bill.amount)}</span></div>
          </div>`
        : `<button class="btn ghost block" id="cekBtn">${ico("search")}Cek Tagihan</button>`;
      const cb = $("#cekBtn"); if (cb) cb.onclick = checkBill;
      return;
    }
    let items = DATA.products[state.cat] || DATA.products.pulsa;
    if (state.cat === "data") {
      const op = detectOp($("#target").value) || "Telkomsel";
      items = items.map(p => ({...p, name: op + " " + p.name}));
    }
    area.innerHTML = `<span class="label" style="display:block;margin-bottom:8px">Pilih nominal</span><div class="prods">` + items.map(p =>
      `<button class="prod${state.product && state.product.code===p.code?' on':''}" data-code="${p.code}"><span class="n">${esc(p.name)}</span><span class="d">${esc(p.desc)}</span><span class="p">${rp(p.price)}</span></button>`).join("") + `</div>`;
    $$(".prod", area).forEach(b => b.onclick = () => { state.product = items.find(p => p.code === b.dataset.code); renderProducts(); renderSummary(); });
  }
  function checkBill(){
    const v = $("#target").value;
    if (v.length < 6){ toast("Nomor pelanggan minimal 6 digit"); return; }
    const btn = $("#cekBtn"); btn.disabled = true; btn.textContent = "Mengecek tagihan…";
    setTimeout(() => {
      const seed = [...v].reduce((a,c) => a + +c, 0);
      const names = ["Sutrisno Wijaya","Dewi Lestari","Ahmad Fauzi","Siti Rahmawati","Bambang Hartono","Nur Aisyah"];
      const map = {
        plnpasca: { base: 285000, extra: [["Tarif/Daya","R1/1300 VA"],["Stand meter","18.240 - 18.519"]], admin: 2750, label: "PLN Pascabayar" },
        pdam:     { base: 98000,  extra: [["Wilayah","PDAM Tirta Kerta Raharja"],["Pemakaian","21 m³"]], admin: 2500, label: "PDAM" },
        bpjs:     { base: 105000, extra: [["Jumlah peserta","3 orang"],["Kelas","Kelas II"]], admin: 2500, label: "BPJS Kesehatan" },
        tv:       { base: 189000, extra: [["Paket","Family HD"],["Provider","TV Kabel Nusantara"]], admin: 2500, label: "TV Kabel" },
        internet: { base: 315000, extra: [["Paket","50 Mbps"],["Provider","IndiHome"]], admin: 2500, label: "Internet Rumah" },
      }[state.cat];
      const amount = state.cat === "bpjs" ? 315000 : map.base + seed * 1750;
      state.bill = { name: names[seed % names.length], period: "Oktober 2026", extra: map.extra, amount, admin: map.admin, label: map.label };
      state.product = { code: "BILL", name: map.label, price: amount + map.admin };
      renderProducts(); renderSummary();
    }, 700);
  }
  function renderSummary(){
    const c = catOf(state.cat), t = $("#target").value, p = state.product;
    const admin = state.bill ? state.bill.admin : 0;
    const total = p ? p.price : 0;
    const ready = p && t.length >= 6;
    $("#summary").innerHTML = `
      <div class="sec-h" style="margin-bottom:10px"><h2>Ringkasan</h2></div>
      ${p ? `<div class="bill" style="background:none;border:0;padding:0">
          <div class="kv"><span>Layanan</span><span>${esc(c.name)}</span></div>
          <div class="kv"><span>Tujuan</span><span class="num">${esc(t || "-")}</span></div>
          <div class="kv"><span>Produk</span><span>${esc(p.name)}</span></div>
          ${admin ? `<div class="kv"><span>Tagihan</span><span class="num">${rp(state.bill.amount)}</span></div><div class="kv"><span>Biaya admin</span><span class="num">${rp(admin)}</span></div>` : ""}
          <div class="kv total"><span>Total bayar</span><span>${rp(total)}</span></div>
          <div class="kv"><span>Saldo setelah</span><span class="num" style="color:${state.saldo-total<0?'var(--bad)':'inherit'}">${rp(state.saldo - total)}</span></div>
        </div>`
        : `<div class="empty">${c.type === "postpaid" ? "Cek tagihan untuk melihat total bayar." : "Pilih nominal untuk melihat total bayar."}</div>`}
      <button class="btn block" id="buyBtn" style="margin-top:14px" ${ready ? "" : "disabled"}>${state.saldo - total < 0 && p ? "Saldo tidak cukup" : "Bayar sekarang"}</button>
      ${!ready && p ? `<p class="hint" style="margin:8px 0 0;text-align:center">Isi nomor tujuan minimal 6 digit.</p>` : ""}`;
    const b = $("#buyBtn"); if (b && ready) b.onclick = () => state.saldo - total < 0 ? (toast("Saldo tidak cukup, isi saldo dulu"), go("deposit")) : confirmPay();
  }

  /* ---------- Modal ---------- */
  function openModal(html){
    const m = $("#modal"); m.hidden = false;
    m.innerHTML = `<div class="overlay" id="ov"><div class="sheet" role="dialog" aria-modal="true"><span class="grab"></span>${html}</div></div>`;
    $("#ov").onclick = e => { if (e.target.id === "ov") closeModal(); };
  }
  function closeModal(){ $("#modal").hidden = true; $("#modal").innerHTML = ""; }
  document.addEventListener("keydown", e => { if (e.key === "Escape") closeModal(); });

  function confirmPay(){
    const c = catOf(state.cat), p = state.product, t = $("#target").value;
    openModal(`<h3>Konfirmasi pembayaran</h3>
      <div class="bill">
        <div class="kv"><span>Produk</span><span>${esc(p.name)}</span></div>
        <div class="kv"><span>${esc(c.input)}</span><span class="num">${esc(t)}</span></div>
        <div class="kv"><span>Metode</span><span>Saldo Feri Bayarin</span></div>
        <div class="kv total"><span>Total</span><span>${rp(p.price)}</span></div>
      </div>
      <div class="field"><label class="label" for="pin">PIN transaksi (demo: 123456)</label>
        <input class="input num" id="pin" type="password" inputmode="numeric" maxlength="6" placeholder="••••••" autocomplete="off"></div>
      <span class="hint" id="pinErr" style="color:var(--bad)" hidden>PIN salah. Gunakan 123456 untuk demo.</span>
      <div style="display:grid;grid-template-columns:1fr 1.4fr;gap:10px">
        <button class="btn ghost" id="cancel">Batal</button><button class="btn" id="ok">Bayar ${rp(p.price)}</button></div>`);
    $("#pin").focus();
    $("#cancel").onclick = closeModal;
    const submit = () => { if ($("#pin").value !== "123456"){ $("#pinErr").hidden = false; return; } process(); };
    $("#ok").onclick = submit;
    $("#pin").addEventListener("keydown", e => { if (e.key === "Enter") submit(); });
  }
  function process(){
    const ok = $("#ok"); ok.disabled = true; ok.textContent = "Memproses…";
    setTimeout(() => {
      const c = catOf(state.cat), p = state.product, t = $("#target").value;
      const now = new Date(), pad = n => String(n).padStart(2,"0");
      const id = "TRX" + String(now.getFullYear()).slice(2) + pad(now.getMonth()+1) + pad(now.getDate()) + String(Math.floor(Math.random()*9000)+1000);
      const status = state.cat === "game" && Math.random() < .3 ? "Pending" : "Sukses";
      let sn = "-";
      if (status === "Sukses") sn = state.cat === "pln"
        ? Array.from({length:5}, () => String(Math.floor(Math.random()*10000)).padStart(4,"0")).join("-")
        : "SN" + Math.floor(Math.random()*1e12).toString().padStart(12,"0");
      let name = p.name; if (state.cat === "pulsa") name = (detectOp(t) || "Pulsa") + " " + p.name.replace("Pulsa ","");
      const tx = { id, date: `${now.getFullYear()}-${pad(now.getMonth()+1)}-${pad(now.getDate())} ${pad(now.getHours())}:${pad(now.getMinutes())}`, cat: state.cat, product: name, target: t, amount: p.price, status, sn };
      state.tx.unshift(tx); state.saldo -= p.price; state.poin += Math.floor(p.price / 1000);
      state.product = null; state.bill = null; $("#target").value = "";
      renderSaldo(); renderRecent(); renderStats(); renderHistory(); renderProducts(); renderSummary(); updateOp();
      showReceipt(tx, true);
    }, 900);
  }
  function showReceipt(t, fresh){
    if (!t) return;
    const c = catOf(t.cat) || {name:"-", input:"Tujuan"};
    const cls = t.status === "Sukses" ? "" : t.status === "Pending" ? " pend" : " fail";
    const ic = t.status === "Sukses" ? "check" : t.status === "Pending" ? "hour" : "x";
    const head = t.status === "Sukses" ? (fresh ? "Pembayaran berhasil" : "Transaksi sukses") : t.status === "Pending" ? "Sedang diproses" : "Transaksi gagal";
    openModal(`<div class="receipt"><span class="ok${cls}">${ico(ic)}</span><h3>${head}</h3><span class="hint num">${t.id} · ${t.date}</span></div>
      <div class="bill">
        <div class="kv"><span>Layanan</span><span>${esc(c.name)}</span></div>
        <div class="kv"><span>Produk</span><span>${esc(t.product)}</span></div>
        <div class="kv"><span>${esc(c.input)}</span><span class="num">${esc(t.target)}</span></div>
        <div class="kv"><span>Status</span><span><span class="pill ${t.status}">${t.status}</span></span></div>
        <div class="kv total"><span>Total</span><span>${rp(t.amount)}</span></div>
      </div>
      ${t.status === "Sukses" ? `<div><span class="label">${t.cat === "pln" ? "Token listrik" : "Serial number / Ref"}</span><div class="sn" style="margin-top:6px">${esc(t.sn)}</div></div>` : ""}
      ${t.status === "Gagal" ? `<p class="hint" style="margin:0">Dana ${rp(t.amount)} sudah dikembalikan ke saldo.</p>` : ""}
      ${t.status === "Pending" ? `<p class="hint" style="margin:0">Biasanya selesai dalam 1–5 menit. Status akan diperbarui otomatis.</p>` : ""}
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px">
        ${t.status === "Sukses" ? `<button class="btn ghost" id="cpSn">Salin ${t.cat === "pln" ? "token" : "SN"}</button>` : `<button class="btn ghost" data-toast="Tiket bantuan dibuat untuk ${t.id}">Bantuan</button>`}
        <button class="btn" id="done">Selesai</button></div>`);
    $("#done").onclick = closeModal;
    const cp = $("#cpSn"); if (cp) cp.onclick = () => (navigator.clipboard ? navigator.clipboard.writeText(t.sn) : Promise.reject()).then(() => toast("Disalin ke clipboard"), () => toast(t.sn));
  }

  /* ---------- Riwayat ---------- */
  function renderHistory(){
    const q = state.q.toLowerCase();
    const rows = state.tx.filter(t => (state.filter === "Semua" || t.status === state.filter) &&
      (!q || [t.id, t.product, t.target].some(x => x.toLowerCase().includes(q))));
    $("#histTable").innerHTML = rows.length ? rows.map(t =>
      `<tr data-tx="${t.id}"><td class="num" style="color:var(--muted)">${t.date}</td><td class="num">${t.id}</td><td><b>${esc(t.product)}</b></td><td class="num">${esc(t.target)}</td><td class="num" style="text-align:right">${rp(t.amount)}</td><td><span class="pill ${t.status}">${t.status}</span></td></tr>`).join("")
      : `<tr><td colspan="6" class="empty">Tidak ada transaksi yang cocok.</td></tr>`;
    $("#histList").innerHTML = rows.length ? rows.map(txRow).join("") : `<div class="empty">Tidak ada transaksi yang cocok.</div>`;
    bindTx($("#histTable")); bindTx($("#histList"));
  }
  $("#q").addEventListener("input", e => { state.q = e.target.value; renderHistory(); });
  $$("#statusSeg button").forEach(b => b.onclick = () => { state.filter = b.dataset.s; $$("#statusSeg button").forEach(x => x.classList.toggle("on", x === b)); renderHistory(); });

  /* ---------- Deposit ---------- */
  const CHIPS = [50000, 100000, 200000, 300000, 500000, 1000000];
  const MI = { bca:"BCA", mandiri:"MDR", bri:"BRI", qris:"QRIS", retail:"RTL" };
  function depFee(){ const m = DATA.deposits.find(d => d.code === state.depMethod); return m.fee < 1 ? Math.ceil(state.depAmt * m.fee) : m.fee; }
  function renderDeposit(){
    $("#depChips").innerHTML = CHIPS.map(v => `<button class="${v===state.depAmt?'on':''}" data-v="${v}">${(v/1000).toLocaleString("id-ID")}rb</button>`).join("");
    $$("#depChips button").forEach(b => b.onclick = () => { state.depAmt = +b.dataset.v; $("#depAmt").value = state.depAmt.toLocaleString("id-ID"); renderDeposit(); });
    $("#methods").innerHTML = DATA.deposits.map(d => `<label class="method"><input type="radio" name="dm" id="dm-${d.code}" value="${d.code}" ${d.code===state.depMethod?"checked":""}>
      <span class="mi">${MI[d.code]}</span><span class="mt">${esc(d.method)}</span><span class="mf">${d.fee === 0 ? "Gratis" : d.fee < 1 ? "0,7%" : rp(d.fee)}</span></label>`).join("");
    $$("#methods input").forEach(i => i.onchange = () => { state.depMethod = i.value; renderDepSummary(); });
    renderDepSummary();
  }
  function renderDepSummary(){
    const fee = depFee(), ok = state.depAmt >= 10000;
    $("#depSummary").innerHTML = `<div class="sec-h" style="margin-bottom:10px"><h2>Ringkasan deposit</h2></div>
      <div class="bill" style="background:none;border:0;padding:0">
        <div class="kv"><span>Nominal</span><span class="num">${rp(state.depAmt)}</span></div>
        <div class="kv"><span>Biaya</span><span class="num">${fee ? rp(fee) : "Gratis"}</span></div>
        <div class="kv total"><span>Total transfer</span><span>${rp(state.depAmt + fee)}</span></div>
      </div>
      <button class="btn block" id="depBtn" style="margin-top:14px" ${ok ? "" : "disabled"}>Buat tagihan deposit</button>
      ${ok ? "" : `<p class="hint" style="margin:8px 0 0;text-align:center">Minimal deposit Rp10.000.</p>`}`;
    const b = $("#depBtn"); if (b && ok) b.onclick = showDeposit;
  }
  $("#depAmt").addEventListener("input", e => {
    const v = +e.target.value.replace(/\D/g, "").slice(0, 9) || 0;
    state.depAmt = v; e.target.value = v ? v.toLocaleString("id-ID") : "";
    $$("#depChips button").forEach(b => b.classList.toggle("on", +b.dataset.v === v)); renderDepSummary();
  });
  function showDeposit(){
    const m = DATA.deposits.find(d => d.code === state.depMethod), total = state.depAmt + depFee();
    const va = m.code === "qris" ? null : m.code === "retail" ? "BYR" + Math.floor(Math.random()*1e9) : "8077" + "0812345678" + String(Math.floor(Math.random()*100)).padStart(2,"0");
    openModal(`<h3>Selesaikan pembayaran</h3>
      <div class="bill">
        <div class="kv"><span>Metode</span><span>${esc(m.method)}</span></div>
        <div class="kv total"><span>Total transfer</span><span>${rp(total)}</span></div>
        <div class="kv"><span>Bayar sebelum</span><span>${new Date(Date.now()+864e5).toLocaleDateString("id-ID",{day:"numeric",month:"short",year:"numeric"})}, 23:59</span></div>
      </div>
      ${va ? `<div><span class="label">${m.code === "retail" ? "Kode pembayaran" : "Nomor Virtual Account"}</span><div class="sn" style="margin-top:6px">${va}</div></div>`
           : `<div style="display:grid;place-items:center;padding:8px"><canvas id="qr" width="180" height="180" style="border-radius:10px;background:#fff"></canvas><span class="hint">QRIS dummy · ${rp(total)}</span></div>`}
      <div style="display:grid;grid-template-columns:1fr 1.4fr;gap:10px">
        <button class="btn ghost" id="cancel">Nanti saja</button><button class="btn" id="paid">Saya sudah bayar</button></div>`);
    if (!va) drawQR($("#qr"));
    $("#cancel").onclick = closeModal;
    $("#paid").onclick = () => { state.saldo += state.depAmt; renderSaldo(); closeModal(); toast("Deposit " + rp(state.depAmt) + " masuk ke saldo (simulasi)"); go("home"); };
  }
  function drawQR(cv){ // pola QR dummy (bukan QR asli)
    const x = cv.getContext("2d"), n = 25, s = cv.width / n; x.fillStyle = "#fff"; x.fillRect(0,0,cv.width,cv.height); x.fillStyle = "#10292b";
    let seed = 7; const r = () => (seed = (seed * 9301 + 49297) % 233280) / 233280;
    for (let i=0;i<n;i++) for (let j=0;j<n;j++) if (r() > .52) x.fillRect(i*s, j*s, s, s);
    [[0,0],[n-7,0],[0,n-7]].forEach(([a,b]) => { x.fillStyle="#10292b"; x.fillRect(a*s,b*s,7*s,7*s); x.fillStyle="#fff"; x.fillRect((a+1)*s,(b+1)*s,5*s,5*s); x.fillStyle="#10292b"; x.fillRect((a+2)*s,(b+2)*s,3*s,3*s); });
  }

  /* ---------- Tema ---------- */
  $("#themeBtn").onclick = () => {
    const r = document.documentElement, dark = r.dataset.theme ? r.dataset.theme === "dark" : matchMedia("(prefers-color-scheme: dark)").matches;
    r.dataset.theme = dark ? "light" : "dark";
    try { localStorage.setItem("bayarin-theme", r.dataset.theme); } catch(e) {}
  };
  try { const th = localStorage.getItem("bayarin-theme"); if (th) document.documentElement.dataset.theme = th; } catch(e) {}

  /* ---------- Init ---------- */
  renderHome(); renderTabs(); selectCat("pulsa"); renderHistory(); renderDeposit(); renderSaldo();
  const h = (location.hash || "").slice(1); if (["home","pay","history","deposit","account"].includes(h)) go(h);

  /* ---------- Logout ---------- */
  $("#logoutBtn").onclick = () => openModal(`<h3>Keluar dari akun?</h3>
    <p class="hint" style="margin:0">Kamu perlu login lagi untuk membuka dashboard.</p>
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px">
      <button class="btn ghost" id="cancel">Batal</button><button class="btn" id="doLogout" style="background:var(--bad);color:#fff">Keluar</button></div>`) || bindLogout();
  function bindLogout(){
    $("#cancel").onclick = closeModal;
    $("#doLogout").onclick = () => {
      closeModal();
      if (<?= $preview ? 'true' : 'false' ?> && window.__fbLogout) { go("home"); window.__fbLogout(); }
      else location.href = location.pathname + "?logout=1";
    };
  }
})();
</script>
<?php endif; ?>
</body>
</html>
