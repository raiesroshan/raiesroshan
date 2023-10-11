
import java.util.PriorityQueue;
import java.util.Comparator;

class Event {
    int time;
    String event;

    public Event(int time, String event) {
        this.time = time;
        this.event = event;
    }
}

class EventComparator implements Comparator<Event> {
    public int compare(Event a, Event b) {
        return a.time - b.time;
    }
}

public class DiscreteEventSimulation {
    public static void main(String[] args) {
        PriorityQueue<Event> eventQueue = new PriorityQueue<>(new EventComparator());

        // Add events to the queue
        eventQueue.add(new Event(1, "Car arrives at traffic light"));
        eventQueue.add(new Event(3, "Traffic light turns green"));
        eventQueue.add(new Event(4, "Car leaves the intersection"));

        // Process events in the queue
        while (!eventQueue.isEmpty()) {
            Event currentEvent = eventQueue.poll();
            System.out.println("Current time: " + currentEvent.time + ", Event: " + currentEvent.event);
        }
    }
}
