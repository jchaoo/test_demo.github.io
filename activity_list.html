<?php
session_start();

$host = '192.168.100.20';
$dbname = 'I4010_9956';
$user = 'ui4b45';
$pass = 'Esas0914';

try {
    $pdo = new PDO("mysql:host=$host;dbname=$dbname;charset=utf8", $user, $pass);
} catch (PDOException $e) {
    die("資料庫連線失敗：" . $e->getMessage());
}

$filter_type = $_GET['event_type'] ?? '';
$filter_name = $_GET['event_name'] ?? '';

$sql = "SELECT * FROM CoupleEvents WHERE 1=1";
$params = [];

if ($filter_type) {
    $sql .= " AND event_type = ?";
    $params[] = $filter_type;
}
if ($filter_name) {
    $sql .= " AND event_name = ?";
    $params[] = $filter_name;
}

$stmt = $pdo->prepare($sql);
$stmt->execute($params);
$events = $stmt->fetchAll(PDO::FETCH_ASSOC);

// 從 CoupleClubs 抓取所有類別
$allClubTypes = $pdo->query("SELECT DISTINCT category FROM CoupleClubs ORDER BY category")
                    ->fetchAll(PDO::FETCH_COLUMN);

// 如果有選社團類別，只抓該類別的社團名稱
if ($filter_type) {
    $nameStmt = $pdo->prepare("SELECT name FROM CoupleClubs WHERE category = ? ORDER BY name");
    $nameStmt->execute([$filter_type]);
    $allClubNames = $nameStmt->fetchAll(PDO::FETCH_COLUMN);
} else {
    $allClubNames = [];
}
?>

<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <title>活動清單</title>
    <style>
        body {
            font-family: "\u5FAE\u8EDF\u6B63\u9ED1\u9AD4", sans-serif;
            background-color: #d4ede7;
            padding: 30px;
        }
        h2 {
            text-align: center;
        }
        form {
            text-align: center;
            margin-bottom: 20px;
        }
        select {
            padding: 5px;
            font-size: 14px;
            margin: 0 5px;
        }
        table {
            width: 90%;
            margin: 0 auto;
            border-collapse: collapse;
            background: white;
        }
        th, td {
            padding: 10px;
            border: 1px solid #999;
            text-align: center;
        }
        th {
            background-color: #E9ECEB;
        }
        .center-text {
            text-align: center;
            margin-top: 20px;
        }
    </style>
</head>
<body>
<h2>活動清單</h2>
<form method="get">
    社團類別：<select name="event_type" onchange="this.form.submit()">
        <option value="">--全部--</option>
        <?php foreach ($allClubTypes as $type): ?>
            <option value="<?= htmlspecialchars($type) ?>" <?= $filter_type == $type ? 'selected' : '' ?>><?= htmlspecialchars($type) ?></option>
        <?php endforeach; ?>
    </select>
    社團名稱：<select name="event_name">
        <option value="">--全部--</option>
        <?php foreach ($allClubNames as $name): ?>
            <option value="<?= htmlspecialchars($name) ?>" <?= $filter_name == $name ? 'selected' : '' ?>><?= htmlspecialchars($name) ?></option>
        <?php endforeach; ?>
    </select>
    <button type="submit">搜尋</button>
</form>

<table>
    <tr>
        <th>名稱</th>
        <th>類別</th>
        <th>日期</th>
        <th>說明</th>
        <th>容量</th>
    </tr>
    <?php foreach ($events as $event): ?>
    <tr>
        <td><?= htmlspecialchars($event['event_name']) ?></td>
        <td><?= htmlspecialchars($event['event_type']) ?></td>
        <td><?= htmlspecialchars($event['event_date']) ?></td>
        <td><?= htmlspecialchars($event['description']) ?></td>
        <td><?= htmlspecialchars($event['capacity']) ?></td>
    </tr>
    <?php endforeach; ?>
</table>
<p class="center-text"><a href="index.php">回首頁</a></p>
</body>
</html>
