# Info module

## Functionaliteit

Voor de info maken we gebruiken van een wysiwyg editor \(What you see is what you get\). Hierdoor kunnen gebruikers makkelijk teksten typen, foto’s toevoegen, en gebruik maken van verschillende opmaakopties



## User journey

1. Gebruikers kunnen in een wysiwyg editor teksten typen, afbeeldingen invoegen en gebruikmaken van verschillende opmaakopties

![](https://lh3.googleusercontent.com/GGNunQb1hG594MUAQ32jApFZoQGBPkbHmH6pL1OaRUc_IDWx3rz4UAExXyq5eL_h3d_V5lfO44ARbTvegcXR7pNisJpGiEPTiv-ViO241vEWbHJ97wUQGyE9LymldYikKcAA08wP)

## Techniek

De input van de tekst wordt omgezet in html en als een blob \(VARCHAR\) opgeslagen per stream.



```text
<?php

namespace App\Http\Controllers\Modules\Info;

use App\Info;
use App\Pollanswer;
use Illuminate\Http\Request;
use App\Http\Controllers\Controller;
use Carbon\Carbon;
use App\Stream;
use Illuminate\Support\Facades\App;
use Illuminate\Support\Facades\Auth;


class InfoApiController extends Controller
{
    /**
     * Create a new controller instance.
     *
     * @return void
     */
    public function __construct()
    {
    }

    /**
     * Show the application dashboard.
     *
     * @return \Illuminate\Http\Response
     */
    public function getInfo(Request $request)
    {
        //TODO: Mag de user deze info wel opvragen
        $info = \App\Info::where('stream_id', '=',$request->input('stream_id'))->first();


        return json_encode($info);


    }



}
```

database:

```text
-- phpMyAdmin SQL Dump
-- version 4.8.3
-- https://www.phpmyadmin.net/
--
-- Host: 127.0.0.1
-- Gegenereerd op: 16 jan 2019 om 17:59
-- Serverversie: 10.1.36-MariaDB
-- PHP-versie: 7.2.10

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `webcast`
--

-- --------------------------------------------------------

--
-- Tabelstructuur voor tabel `infos`
--

CREATE TABLE `infos` (
  `id` int(11) NOT NULL,
  `stream_id` int(11) NOT NULL,
  `text` varchar(5120) NOT NULL,
  `created_at` datetime NOT NULL,
  `updated_at` datetime NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Gegevens worden geëxporteerd voor tabel `infos`
--

INSERT INTO `infos` (`id`, `stream_id`, `text`, `created_at`, `updated_at`) VALUES
(1, 8, '<a href=\\\"\\\\&quot;tetje.sdfjkhsdfkjdhf.nl\\\\&quot;\\\" title=\\\"\\\\&quot;test\\\\&quot;\\\">c</a>bncvhjghmghmhgnxfgncfgbn', '2018-11-21 12:35:26', '2018-12-04 15:33:08'),
(2, 10, 'dikke onzin', '2018-12-11 00:00:39', '2018-12-11 00:00:39'),
(3, 11, '<h1><strong>Hoe kies je de studie ie bij jou past?</strong></h1><p>Het allerbelangrijkste bij het kiezen van een studie ben jij. Als je \r\nweet wie jij bent, kun je beter bepalen wat bij je past. Stel jezelf \r\ndaarom vragen: Wat wil ik? Waar ben ik goed in? Wat vind ik leuk? Maar \r\nook wat vind ik niet leuk en waar ben ik minder goed in? Stel deze \r\nvragen ook eens aan anderen. Hoe zien zij jou?</p>\r\n\r\n<p>Maak een profiel van jezelf. Daarmee kun je bij opleidingen gaan \r\nkijken of die voldoen aan jouw eigenschappen en wensen. Zo kies je een \r\nopleiding die bij je past.</p>', '2018-12-16 19:58:56', '2018-12-16 20:29:34'),
(4, 12, 'guhgfjhgfvhjgfvfmjhgfvhjgfv', '2018-12-17 10:54:25', '2018-12-17 10:54:25'),
(5, 13, 'Ik ben daimy!!!', '2019-01-10 22:13:53', '2019-01-10 22:13:53');

--
-- Indexen voor geëxporteerde tabellen
--

--
-- Indexen voor tabel `infos`
--
ALTER TABLE `infos`
  ADD PRIMARY KEY (`id`);

--
-- AUTO_INCREMENT voor geëxporteerde tabellen
--

--
-- AUTO_INCREMENT voor een tabel `infos`
--
ALTER TABLE `infos`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=6;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;

```

