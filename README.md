import java.time.Duration;
import java.time.LocalDateTime;
import java.time.ZoneId;
import java.time.ZonedDateTime;

public class MyForm {
    public static void main(String[] args) {
        ZonedDateTime arriveltime = ZonedDateTime.of(2022, 11, 26, 23, 45, 0, 0, ZoneId.of("Europe/Moscow"));
        ZonedDateTime destinationTime = ZonedDateTime.of(2022, 11, 27, 16, 25, 0, 0, ZoneId.of("Asia/Magadan"));
        ZonedDateTime destinationTimeInMoscow = destinationTime.withZoneSameInstant(ZoneId.of("Europe/Moscow"));
        System.out.println(arriveltime);
        System.out.println(destinationTimeInMoscow);
        LocalDateTime destinationTimeInLocalMoscow = destinationTimeInMoscow.toLocalDateTime();
        LocalDateTime arriveltimeLocal = arriveltime.toLocalDateTime();
        Duration duration = Duration.between(arriveltimeLocal, destinationTimeInLocalMoscow);

        System.out.printf(
                "%dч %dмин%n",
                duration.toHours() % 24,
                duration.toMinutes() % 60
        );
    }
}
